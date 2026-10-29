# Research and Conference Hunter

**Status:** stage 1 built and run end to end in n8n 2026-10-29 (search or own list, dedupe, screen, PRISMA counts, token budget). Zotero push and conference branch not built. Not shipped.
**Deadline:** 2026-10-31 (see the author's private plan for the full timeline).

## Problem and goal
One topic in. Parallel searches of scholarly sources and conference call-for-papers pages, dedupe, AI screens each paper against written criteria with a reason, PRISMA count sheet, approved papers pushed to Zotero.

**Design decision (2026-10-27):** no vector database. It is added only if `eval.md` shows it improves recall.

## Success criterion
Seeded-pool test (replaced the original 80%-recall target, reasons in `eval.md`): mix 35 known SLR papers into unrelated search results and measure how many the screener keeps. Results are in `eval.md`.

## How the workflow is laid out (stage 1, draft, 2026-10-29)
Workflow name in n8n: `P1 Research and Conference Hunter (stage 1)`. Three groups on the canvas, plus one output branch.

| Section | Nodes | What it does | You edit |
|---|---|---|---|
| **1 Search and dedupe** | Run Inputs, Search OpenAlex, Split Results, Rebuild Abstract, Normalize DOI, Remove Duplicates, Limit Papers | Run Inputs holds every setting for a run. Search OpenAlex fetches pages of 100 works, retrying on failure. Split Results turns each page into one item per paper. Rebuild Abstract turns OpenAlex's word-position index back into readable text. Normalize DOI lowercases the DOI and strips the URL prefix. Remove Duplicates drops repeat DOIs. Limit Papers caps how many papers reach the LLM. | `research_question`, `search_query`, `from_year`, `max_pages`, `max_papers`, `inclusion_criteria`, `exclusion_criteria` in Run Inputs |
| **2 Screen with the LLM** | Screen Paper, Groq Chat Model, Screening Decision, Screening Result | One LLM call per paper, with no memory so papers cannot influence each other. The model reads title, year and abstract against your written criteria. The Screening Decision parser forces the answer into `decision` (include, exclude or maybe), `reason` and `criterion`. Screening Result joins that answer back to the paper's DOI, title and year. | Nothing, except the model in Gemini Chat Model |
| **3 PRISMA counts** | Collect Decisions, PRISMA Counts | Collects all decisions into one item, then writes the six PRISMA numbers: identified, duplicates removed, screened, included, maybe, excluded. | Nothing |
| **Output branch** | Included Papers | A filter that keeps only `decision = include`. This list is what a human reviews before anything goes to Zotero (stage 2, not built). | Nothing |

Cost control: see Token controls below.

**Not built yet:** Zotero push and approval step, the conference call-for-papers branch, parser auto-fix. The research question and criteria in Run Inputs are the ICWIHI 2025 SLR ones; replace them with your own.

## Two ways to use it (tested 2026-10-29)
Set `mode` in Run Inputs. Same workflow, same screening, different starting point.

| `mode` | You have | What runs | Tested |
|---|---|---|---|
| `search` | a topic, no papers | OpenAlex search only (`search_query`) | execution 14, free keyword screener |
| `my_papers` | an already sorted list of papers | only your `my_dois` list, no search | execution 15, Groq AI, 9 papers |
| `both` | a list plus a search | your list first, then search results | execution 16, keyword screener, 135 papers |

`my_dois` accepts DOIs separated by new lines, commas, spaces or `|`, with or without `https://doi.org/`. Long lists are cut into groups of 50 automatically. PRISMA Counts reports how many of your DOIs OpenAlex found (`my_list_requested` vs `my_list_found_in_openalex`) and how many the screener kept (`my_list_kept_percent`).

## Token controls (all in Run Inputs)
| Setting | What it does |
|---|---|
| `max_abstract_chars` (1000) | cuts each abstract before it goes to the AI |
| `token_budget` (100000) and `tokens_per_paper` (1100) | the paper cap is `min(max_papers, token_budget / tokens_per_paper)`. Papers over the cap are not screened and are counted in `not_screened_over_budget` |
| `skip_first` | continue a long list: set it to the number of papers already screened |
| `use_llm` false | free keyword screener (`keywords_a`, `keywords_b`), zero tokens |
| no abstract | the paper is not sent to the AI and is marked `maybe` for a human look |

Measured: 9 AI calls used 9,582 tokens, 1,065 per paper (about 914 prompt, 172 answer). Groq free limit is 8,000 tokens per minute, so the 12 second pace stays. PRISMA Counts shows `sent_to_ai` and `est_tokens_used`.

## Step 4: extract facts (optional, tested 2026-10-29)
Set `extract` to true in Run Inputs. For each paper in scope, Groq reads the abstract and fills `study_type`, `technology`, `participants`, `outcomes`, `main_finding` (`not stated` when the abstract does not say). Output node: `Extraction Table`.
- `extract_scope`: `my_list` = every paper from your own list; anything else = papers the screener kept (include or maybe).
- Cap: `extract_budget` / `tokens_per_extraction` papers (30000 / 1250 = 24). Papers without an abstract are skipped.
- Measured (execution 18): 10 papers, 12,374 tokens, 1,237 per paper. 9 clean rows, 1 row flagged `extraction failed` (the AI answer could not be parsed; the run continues and the row says to fill it by hand).
- Screening got the same protection: an unreadable AI answer becomes `maybe` with a note, not a crashed run.
- Extracted facts come from the abstract only. Check them before use.

## Still to write when this ships
- [ ] Diagram
- [ ] Setup steps
- [ ] Credentials needed (names only, see `../../.env.example`)
- [ ] Cost per run
- [x] `workflow.json` (credentials stripped, exported 2026-10-29, see `../../SANITIZATION.md`). Import it in n8n, then pick your own Groq credential in the two Groq model nodes.
- [ ] `screenshot.png`
- [ ] Runs on the bundled sample data with credentials as the only edit
