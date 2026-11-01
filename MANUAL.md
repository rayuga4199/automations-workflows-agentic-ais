# Instruction manual

How to run each project, in order. For depth, see the README in each project folder.

**Before you start:** open Docker, then open n8n at `http://localhost:5678`. Projects 1 to 3 need it. In the two workflow tables, the steps marked "does it for you" need no input.

## 1. [Workflow] Research and Conference Hunter
**You use:** the `Run Inputs` node. Press **Execute workflow** to run.

| Order | Node | What you do |
|---|---|---|
| 1 | `Start` | Nothing. It starts the run |
| 2 | `Run Inputs` | Set `mode` to `search`, `my_papers` or `both` |
| | | For `search`: fill `search_query`, `from_year` and `max_pages` |
| | | For `my_papers`: paste your DOIs into `my_dois` |
| | | Always: fill `research_question`, `inclusion_criteria` and `exclusion_criteria` |
| | | Set `use_llm` to `true` for AI screening, or `false` for free keyword screening |
| | | Optional: set `extract` to `true` for a facts table |
| 3 | `Groq Chat Model`, `Groq Extract Model` | Select your Groq credential. Needed only if `use_llm` or `extract` is `true` |
| 4 | Search, cleaning and screening nodes | Does it for you |
| 5 | Results | Open `Screening Result`, `Included Papers`, `PRISMA Counts` and `Extraction Table` |

## 2. [Workflow] Insight Synthesis Engine
**You use:** the form at `http://localhost:5678/form/insight-engine`. No nodes to edit.

| Order | Where | What you do |
|---|---|---|
| 1 | Form: Research question | Type your question. Required |
| 2 | Form: Interview transcripts | Paste them, with a `---` line between two transcripts |
| 3 | Form: Other text | Paste blogs, notes or reports, with `---` between pieces |
| 4 | Form: Web links | One link per line |
| 5 | Form: Names to hide | Participant names, separated by commas |
| 6 | **Analyse** button | Press it and stay on the page for about 5 minutes |
| 7 | Report page | Check every insight against its quotes |

To change limits, edit `Run Inputs`, then publish again. Normal use needs no change.

## 3. [AI Agent] Research Writer
**You use:** a form to add quotes, then a chat with the agent. It is an unpublished draft, so use its preview chat in n8n.

| Order | Where | What you do |
|---|---|---|
| 1 | `http://localhost:5678/form/add-quote` | Add each source's title and exact quote, plus page, authors, year and DOI if you have them. This form is not tested yet |
| 2 | n8n, **Agents**, `[AI Agent] Research Writer` | Open the agent and its preview chat |
| 3 | Chat | Type one of the requests below |

| To do this | Type |
|---|---|
| Check a draft | `Check this draft against my ledger:` then about 10 numbered sentences |
| Verify a reference | `Verify this reference:` then the DOI or exact title |
| Polish | `Polish this sentence:` then your sentence |
| Find papers | `Find papers on` then your topic. Not tested yet |
| Find gaps | `Find gaps in my ledger on` then your topic. Not tested yet |

## 4. [Agentic AI] Design Team
**You use:** Claude Code with your Claude plan. No nodes.

| Order | Where | What you do |
|---|---|---|
| 1 | VS Code | Open the folder `agentic-ais/01-design-team` |
| 2 | Claude panel | Type `/design-team` followed by what you want to build |
| 3 | Wait | About 10 to 25 minutes. It asks no questions |
| 4 | `reports/<project>/report.md` | Read the full report |
| 5 | `reports/<project>/starter/index.html` | Open the starter site, if you asked for a build |

Say "build" or "code" in your brief to wake the developer.

**Free backup in n8n:** open `http://localhost:5678/form/design-team`, describe what you want, press **Start the team** and stay on the page. It takes about 5 to 7 minutes.

## If something goes wrong
| What you see | What to do |
|---|---|
| A form or node says rate limit | Groq's free limit is used up. Try again later |
| A plain problem message on a form | Follow what it says |
| n8n will not open | Start Docker, then the `n8n` container |
