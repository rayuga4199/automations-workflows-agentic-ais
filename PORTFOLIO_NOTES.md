# Portfolio notes

For the person or AI agent writing the portfolio page. Project facts live in each `PORTFOLIO_BRIEF.md`. This file holds the page decisions and how the author directed the AI. Quotes are the author's own words from the build conversation, kept as typed.

## Page decisions
| Decision | Choice |
|---|---|
| Projects on the page | Four. No others are committed before launch. |
| Deep dives | Insight Synthesis Engine and Design Team. |
| Cards | Literature Review Screener and Research Writer. |
| Design Team visual | An agent file next to a report excerpt, plus `reports/tool-library/starter-page.jpg`. No screenshot of a Claude Code run exists. The n8n canvas images show the backup, so label them that way. |
| Project 1 name | `[Workflow] Literature Review Screener`. It was called Research and Conference Hunter. The name changed because the Zotero push and conference branch are not built. Its folder keeps the old name. |

## How the author directed the AI
1. **Rejected a compact canvas.** On seeing the first Insight Synthesis Engine canvas: "This is not what it is supposed to be look like." The author asked for more space, no overlaps and the extended version, not the compact one. The layout became one long left-to-right flow, and the rule carried over to the other projects.
2. **Ordered a stress test, then a rebuild.** "stress test it", followed by "build me foolproof yet very simple and systematic. Change everything if you need to". The tests found names that were not hidden and failed runs that still looked successful. The rebuild added a form, a check after each stage and plain-language stop pages. See `workflows/02-insight-synthesis-engine/eval.md`.
3. **Refused paid API access.** "I don't want to use API. I already have Claude's Pro subscription". A Pro login cannot be used inside n8n, so the main Design Team moved to Claude Code and the n8n version became the backup. See `agentic-ais/01-design-team/README.md`.
4. **Held the team to a written list.** The author required each agent to have a name, its own memory, experience and knowledge, and to stay updated: "make sure you tick every point from this list". Testing then found one agent saved no memory and another wrote no `MEMORY.md`, so saving memory became a mandatory step. See `agentic-ais/01-design-team/eval.md`.
5. **Set the standard for evidence.** On screenshots: "make sure you capture everything". Meeting that standard exposed real overlaps in three projects, so the layouts were fixed, not just photographed.

## Do not claim
These moments show how the work was directed. They are not evidence that the projects work at scale. Use each brief's limits and caveats.
