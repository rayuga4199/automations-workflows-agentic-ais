# Workflows

Fixed-step automations built in n8n. The steps are drawn in advance; an AI only does bounded jobs inside them (for example "screen this one abstract"), and a human checks the output. One numbered subfolder per project.

| Project | Status | Summary |
|---|---|---|
| [01 \[Workflow\] Research and Conference Hunter](01-research-and-conference-hunter/) | Paper side built and tested. Zotero push and conference branch not built. | Screens papers for a systematic literature review from a topic search or from your own DOI list, with token budget, PRISMA counts and an optional facts table. |
| [02 \[Workflow\] Insight Synthesis Engine](02-insight-synthesis-engine/) | Built and stress tested on small synthetic samples. Not tested at scale or on real interview data. | A form takes transcripts, pasted text and web links, hides listed names, and returns themes and insights with exact quotes. |

## Folder standard
Every project folder holds: `README.md` (problem, architecture diagram, inputs, outputs, setup, credentials by name, cost, limitations, status), `PORTFOLIO_BRIEF.md` (verified facts and allowed claims for whoever writes about it), `workflow.json` (sanitised n8n export), `sample-input/`, `sample-output/` (real data, no copyrighted PDFs), `eval.md` (method and measured results), and `screenshot.png` when available. A missing file is listed as missing in the project README, not hidden.
