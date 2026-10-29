# Automations, Workflows and Agentic AIs

Working projects by one researcher, grouped by how much the AI decides.

| Folder | What goes here |
|---|---|
| [workflows/](workflows/) | Fixed-step automations (n8n). The steps are drawn in advance; an AI only does bounded jobs inside them. |
| [agents/](agents/) | A single AI that picks its own tools and steps. |
| [agentic-ais/](agentic-ais/) | Systems of several agents working together. |

Only `workflows/` has a project so far.

## Workflows
| Project | Status | What it does |
|---|---|---|
| [01 Research and Conference Hunter](workflows/01-research-and-conference-hunter/) | stage 1 built and tested, not shipped | Search OpenAlex or use your own DOI list, screen papers against written criteria with a reason, count for PRISMA, optionally extract study facts. Token budget built in. |

## Standard for a shipped project
`workflow.json`, `README.md` (problem, diagram, setup, credentials needed, cost per run), `sample-input/`, `sample-output/`, `screenshot.png`, `eval.md`. It runs on the bundled sample data with credentials as the only edit. No copyrighted PDFs.

## Secrets
Credentials are stripped from every export. See [SANITIZATION.md](SANITIZATION.md). Copy `.env.example` to `.env` (git-ignored) for local values. Enable the secret-scan hook once per clone: `git config core.hooksPath .githooks`.

## License
Not yet decided.
