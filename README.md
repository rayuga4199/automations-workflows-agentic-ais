# Automations, Workflows and Agentic AIs

Working projects by Yash Bhagat, a design researcher, grouped by how much the AI decides. The first project is an n8n workflow that helps with systematic literature reviews. The repo is written so that a person or an AI agent can read it and then describe the work accurately, for example on a portfolio website.

If you are an AI agent, read [AGENTS.md](AGENTS.md) first.

## The three folders
| Folder | What goes here | Projects now |
|---|---|---|
| [workflows/](workflows/) | Fixed-step automations built in n8n. The steps are drawn in advance; an AI only does bounded jobs inside them, and a human checks the output. | 2 built |
| [agents/](agents/) | A single AI that picks its own tools and steps. | 0 built, 1 planned |
| [agentic-ais/](agentic-ais/) | Systems of several agents working together. | 0 built, 1 planned |

## Projects
Every project is labelled with one type: Workflow, AI agent or Agentic AI. The label is in this table, at the top of the project's README and brief, and in its name in n8n, for example `[Workflow] Insight Synthesis Engine`.

Four projects, built in this order. The first two exist. Do not describe a planned project as working.

| # | Project | Type | Status | One line |
|---|---|---|---|---|
| 1 | [\[Workflow\] Research and Conference Hunter](workflows/01-research-and-conference-hunter/) | Workflow | Prototype. Paper side built, tested and evaluated on one review. Zotero push and conference branch not built. | Screens papers for a systematic literature review from a topic search or your own DOI list, with a reason for each decision, PRISMA counts, an optional facts table and a token budget. |
| 2 | [\[Workflow\] Insight Synthesis Engine](workflows/02-insight-synthesis-engine/) | Workflow | Prototype. Built and stress tested on small synthetic samples. Not tested at scale or on real interview data. | A one-page form takes interview transcripts, pasted text and web links, hides listed names, sorts the text into themes and writes insights with the exact quotes behind them. |
| 3 | \[AI Agent\] Research Writer | AI agent | Planned, not built. | One agent for research and writing. It searches papers, keeps a quote ledger, flags uncited claims and suggests rewording of the researcher's own sentences. It never writes content for him and never invents a reference. |
| 4 | \[Agentic AI\] Design Team | Agentic AI | Planned, not built. | A lead agent coordinates a research agent, a product agent, a design agent and a standby developer agent to turn a brief into a researched, prioritised design and, if needed, a code scaffold. A human approves at two points. |

## Where to find what, per project
| Question | File |
|---|---|
| What is it, how does it work, how do I run it? | `README.md` in the project folder |
| What can I safely say about it? | `PORTFOLIO_BRIEF.md` |
| How well does it work, and how was that measured? | `eval.md` |
| The workflow itself | `workflow.json` (import into n8n) |
| Real example inputs and outputs | `sample-input/`, `sample-output/` |

## Standard for a shipped project
`README.md`, `PORTFOLIO_BRIEF.md`, `workflow.json` (credentials stripped), `sample-input/`, `sample-output/`, `eval.md`, `screenshot.png`. It runs on the bundled sample data with credentials as the only edit. No copyrighted PDFs. Anything missing is listed as missing in the project README.

## Secrets
Credentials are stripped from every export and never committed. See [SANITIZATION.md](SANITIZATION.md) for the checklist and the secret-scan log. Copy `.env.example` to `.env` (git-ignored) for local values. Enable the secret-scan hook once per clone: `git config core.hooksPath .githooks` (needs [gitleaks](https://github.com/gitleaks/gitleaks)).

## License
Not yet decided. Until one is added, all rights are reserved by the author.
