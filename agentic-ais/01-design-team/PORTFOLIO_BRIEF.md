# Portfolio brief: [Agentic AI] Design Team

**Type:** Agentic AI

For the person or AI agent writing the portfolio page. Everything here is checked against this folder. Do not add claims that are not here.

## One-line pitch
A studio of five named AI specialists that takes one sentence about what you want to build and returns research, priorities, a design, a director's review and, if asked, starter code.

## Who made it
Author: Yash Bhagat, a design researcher. Built with Claude Code (an AI coding assistant), with the author directing and reviewing. Say so if the page describes how it was built.

## Verified facts
| Fact | Evidence |
|---|---|
| Five agents, each with a name, personality, fictional career, knowledge, memory folder and web search | `.claude/agents/` |
| The developer wakes only when the brief asks for a build | `eval.md` |
| Two full test briefs completed with no stops, in about 10 and 25 minutes | `eval.md` |
| A hidden instruction in a brief was ignored | `eval.md`, `reports/smartphone-tutoring/` |
| The generated site loaded with no console errors, and its filter and Reserve flow worked | `eval.md`, `reports/tool-library/starter-page.jpg` |
| Runs on a Claude plan with no API key | `README.md` |

## Story to tell
1. The first build ran on free AI models in n8n and hit daily limits.
2. A Claude Pro login cannot be used inside n8n, so the team moved to Claude Code, where each agent can have its own memory folder.
3. Testing found real faults, including agents that saved no memory, and each was fixed and rechecked.

## Claims you may make
- Each agent has its own personality, knowledge and memory folder.
- The agents search the web while they work.
- The team runs from one sentence without stopping for questions.
- Evidence must carry a link, and assumptions are labelled.

## Claims you must NOT make
- Do not say the characters are real, or describe their fictional careers as fact.
- Do not say it replaces designers, researchers or developers.
- Do not say it interviews real users. It writes a research plan.
- Do not say its advice is proven or validated. It was tested on two sample briefs.
- Do not say the generated code is production ready. It is a scaffold.
- Do not say the memory is locked. It is separated by folder and by rule.
- Do not say the models retrain or stay current by themselves. They search when they run.
- Do not say it is a hosted app. It runs in Claude Code.
- Do not invent user numbers, time saved or testimonials. None exist.

## Suggested page structure
1. Title, pitch, status badge ("prototype, tested on two sample briefs").
2. Meet the team (table in `README.md`, labelled fictional).
3. How a brief moves through the studio (Mermaid diagram).
4. What each agent has (table in `README.md`).
5. Sample output (`reports/`, `starter-page.jpg`).
6. What testing found (`eval.md`).
7. Limitations.

## Assets
Available: `reports/tool-library/starter-page.jpg`, two full reports, a generated starter site, the Mermaid diagram.
Missing: a demo video, a screenshot of a run. Do not reference them as if they exist.

## Tone
Plain, specific, first person singular or neutral. No hype words. Numbers always come with their caveat.
