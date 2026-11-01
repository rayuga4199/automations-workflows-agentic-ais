# Eval: [Workflow] Literature Review Screener

**Status (2026-10-29):** seeded-pool test run twice (free keyword screener, then Groq AI screener), plus functional tests of the three input modes, a fresh-import test and the extraction step. All on one local n8n 2.45.6 instance. Terminology note: Runs 1 and 2 were executed before two fields were renamed. Then `seed_dois` was `my_dois`, `is_seed` was `in_my_list`, and the metrics `seeds_*` and `seed_recall_percent` were `my_list_*` and `my_list_kept_percent`. Same meaning.

## Success criterion
Original (2026-10-17): rerun the ICWIHI 2025 SLR question and recover at least 80% of the 35 included papers.

**Replaced 2026-10-29 (the author's decision): seeded-pool test.** Reason: the original target cannot be met by searching. Measured before replacing it:
- Keyword search with the SLR's own search terms, 3 pages of 100 each, 2007 to 2025: 6 of the 35 papers retrieved (17%).
- Citation snowballing, 1 hop, 5 random seeds, 200 trials: about 1 of the other 30. Only 4 citation links exist among the 35 papers, and only 7 of them link to another one. The 35 are a hand-picked multi-topic set, not a citation cluster.

New criterion: mix the 35 papers into a pool of unrelated search results, run the screener, and report (a) **seed recall**: share of the 35 kept as include or maybe, target 80% or more, and (b) the share of the other papers rejected, so a screener that keeps everything cannot pass.

## Method
1. Workflow `[Workflow] Literature Review Screener` (named `P1 Research and Conference Hunter (stage 1)` during these runs) (`workflow.json`), switch `use_llm` in Run Inputs.
2. `my_dois` (then called `seed_dois`) holds the 35 DOIs. One OpenAlex call fetches them first, so the paper cap cannot cut them.
3. `search_query` is run for 3 pages of 100 (300 papers), from 2007.
4. DOIs are lowercased, duplicates removed on DOI, then each paper is screened on title and abstract against the written criteria (`inclusion_criteria`, `exclusion_criteria` in Run Inputs, taken from the ICWIHI 2025 paper).
5. `PRISMA Counts` reports the numbers below. Paper decisions are in `Screening Result` (field `in_my_list`, then `is_seed`, marks the 35).

Inputs: query `mixed reality personal assistant social isolation`, from 2007, 3 pages, cap 400 papers. Screener: free keyword rule (include = mentions MR or AR and an assistant, companion, agent, avatar or chatbot word; maybe = mentions one of them; exclude = neither).

## Results

### Run 1: keyword screener, no AI (2026-10-29, execution 8)
| Measure | Value |
|---|---|
| Papers identified (35 seeds plus 300 search results) | 335 |
| Duplicates removed | 1 |
| Screened | 334 |
| Include / maybe / exclude | 10 / 121 / 203 |
| Seeds in pool | 35 |
| Seeds kept as include | 5 |
| Seeds kept as maybe | 21 |
| Seeds rejected | 9 |
| **Seed recall (include + maybe)** | **74%** (26 of 35). Target 80%: **not met** |
| Other papers rejected | 65% |

Reading this honestly:
- The 74% counts "maybe" as kept, and 121 of 334 papers are "maybe", so the screener is mostly passing the word AR through. It is a baseline, not a result to publish.
- The 9 seeds it rejected are the social media and adolescent well-being papers and the social VR and isolation papers. They do not mention MR or AR, so the keyword rule drops them. Several of them also break the written exclusion criteria (VR only or non-MR), which means the 35 papers are not all consistent with the SLR's own written criteria. Any screener that follows those criteria will reject some of them.
- Only 5 of the 35 are a clean "include". A person reading the include list would see 10 papers, 5 of them from the 35.

### Run 2: AI screener, written criteria (2026-10-29, execution 13)
Screener: Groq `openai/gpt-oss-120b` (free tier), one paper per call, 12 s apart, temperature 0. Pool: the 35 seeds plus 15 search results (50 papers, capped by the free 8,000 tokens-per-minute limit). Run time about 11.5 minutes. Same written criteria as Run 1.

| Measure | Value |
|---|---|
| Screened | 50 |
| Include / maybe / exclude | 4 / 1 / 45 |
| Seeds kept as include | 4 |
| Seeds kept as maybe | 1 |
| Seeds rejected | 30 |
| **Seed recall (include + maybe)** | **14%** (5 of 35). Target 80%: **not met** |
| Other papers rejected | 100% (15 of 15) |

Reading this honestly:
- The AI did its job. Each of the 30 rejections quotes a written criterion, for example "no personal assistant, companion, agent or avatar" or "VR only" or "not MR/AR". It follows the criteria in the ICWIHI 2025 paper literally.
- So the written criteria do not describe what the SLR actually included. Only 5 of the 35 papers are about MR/AR personal assistants, companions or agents. The other 30 are broader: AR in education, AR privacy and security, adolescent social media and well-being, social VR and loneliness, remote assistance, and AR for mental health.
- This is a finding about the SLR's method write-up, not about the workflow. Either the criteria in the paper are narrower than the real inclusion decisions, or the 35 were chosen with looser rules than the ones written down. A reader or reviewer who applies the written criteria would reject 30 of the 35.
- Keyword Screen (Run 1) kept 26 of 35 only because it passes anything that mentions AR; it is not a better screener.

Next test (not run): rewrite the inclusion criteria to match what the 35 actually have in common, then rerun. Recall measured that way tells how well a screener learns the real rule, but it is fitted to the same 35 papers, so it is a ceiling, not an independent score.

## Functional tests of the final workflow (2026-10-29)
These check that the workflow works, not how accurate it is. Counts are in `sample-output/`.

| Test | Settings | Result |
|---|---|---|
| `search` mode | keyword screener, 1 page, cap 50 | Success. 100 papers identified, 50 screened (cap), 50 left over and counted. |
| `my_papers` mode | Groq AI, 35 DOIs, cap 10 | Success. All 35 DOIs found in OpenAlex, 10 screened, 9 sent to the AI (1 had no abstract and became `maybe`), 9,582 tokens used. |
| `both` mode | keyword screener, token budget 100,000 at 1,100 per paper | Success. 135 papers identified, 1 duplicate, 90 screened (budget cap), 44 left over. Your list: 26 of 35 kept (74%), same as Run 1. |
| Fresh import | `workflow.json` imported as a new workflow, no credentials, quickstart settings | Success. 105 identified, 10 screened, 5 of 5 sample DOIs found. |
| Extraction | `my_papers` mode, 10 papers, Groq AI | 9 clean rows, 1 flagged `extraction failed`. 12,374 tokens, 1,237 per paper. An earlier run crashed on a value outside the allowed list (`not stated` for study type); fixed by allowing `not_stated` and by turning an unreadable answer into a flagged row. |

## Limits of this test
- One query, one run, one screener. The numbers can move with the query and the criteria wording.
- The unrelated papers are not labelled by a human, so "other papers rejected" is a rough noise measure, not precision.
- The research question was derived from the paper's stated aim; the paper has no formal research question.
