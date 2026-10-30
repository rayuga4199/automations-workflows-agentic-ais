# Portfolio brief: [Workflow] Research and Conference Hunter

**Type:** Workflow

For the person or AI agent writing the portfolio page for this project. Everything below is checked against the files in this folder. Where a claim has a source, the source is named. Do not add claims that are not here.

## One-line pitch
An n8n workflow that screens research papers for a systematic literature review, either from a topic search or from a list the researcher already has, shows its reason for every decision, counts papers for PRISMA, and keeps AI token use under a budget.

## Who made it and why
- Author: Yash Bhagat, a design researcher (Department of Design, IIT Hyderabad per the ICWIHI 2025 paper header). He wrote the systematic literature review "The Potential of Mixed Reality (MR) companions for navigation - A Systematic literature review" (with Delwyn Jude Remedios) for ICWIHI 2025, and used his own review as the test case.
- Built with Claude Code (an AI coding assistant) through n8n's built-in MCP server, with the author directing and reviewing. Say so if the page describes how it was built.
- Thread across the author's planned workflows: a researcher who automates research operations, with a human verifying every judgement.

## The two use cases (the main selling point)
1. **No papers yet:** give a topic, the workflow searches OpenAlex.
2. **Papers already sorted:** paste DOIs, the workflow fetches those exact papers and screens or analyses them, with no search.
`both` combines them. The same screening, counts and token controls apply to either.

## Verified facts
| Fact | Evidence |
|---|---|
| 45 nodes in 4 groups, 1 Code node, 6 sticky notes | `workflow.json` |
| Runs on n8n 2.45.6 self-hosted in Docker | `README.md`, `eval.md` |
| Data source: OpenAlex, keyless for basic use | `README.md` |
| AI screener: Groq `openai/gpt-oss-120b`, free tier, temperature 0, one paper per call, 12 s pacing | `workflow.json` |
| Screening cost 1,065 tokens per paper (9 calls, 9,582 tokens) | execution data, `eval.md` |
| Extraction cost 1,237 tokens per paper (10 calls, 12,374 tokens) | execution data, `README.md` |
| Token budget caps the number of papers screened: `min(max_papers, token_budget / tokens_per_paper)` | `workflow.json` |
| Keyword search with the review's own terms retrieved 6 of the author's 35 papers (17%) | `eval.md` |
| Seeded-pool test, keyword screener: 26 of 35 papers kept (74%), 65% of other papers rejected | `eval.md`, execution 8 |
| Seeded-pool test, AI screener with the paper's written criteria: 5 of 35 kept (14%), 15 of 15 others rejected | `eval.md`, execution 13 |
| The shipped `workflow.json` imported fresh and ran with no credentials | `sample-output/quickstart-prisma-counts.json` |
| Extraction: 9 of 10 clean rows, 1 flagged for hand filling | `sample-output/extraction-table.sample.json` |

## What the results mean (write it this way)
- The original goal, "recover 80% of the 35 papers by searching", **could not be met**, and the author measured why (6 of 35 by keyword search; about 1 of 30 by citation chasing). He replaced it with a seeded-pool test. Present this as honest method, not failure.
- The AI screener kept only 14% of the 35 because it followed the written criteria literally and 30 of the 35 papers do not match them (they cover AR education, AR privacy, adolescent social media, social VR and loneliness, remote assistance, mental health). The finding is that the review's written criteria are narrower than its actual inclusion decisions. It is not a claim that the AI is accurate or inaccurate.
- The 74% from the keyword screener mostly reflects that "maybe" counts as kept; the author's own note calls it a baseline.

## Claims you may make
- It supports two ways to start (topic search or own DOI list) and a hybrid.
- Every decision carries a reason and the deciding criterion.
- Token use is measured per paper and bounded by a budget, with a zero-token keyword mode.
- Papers without an abstract are never sent to the AI.
- A bad AI answer does not crash the run; it becomes a flagged row.
- It produces PRISMA counts and an optional facts table, and a human checks the output.
- The exported workflow contains no credentials and runs without any API key in its default (keyword) mode.

## Claims you must NOT make
- Do not say it achieved 80% recall, or any accuracy, precision or recall figure beyond those in `eval.md`.
- Do not say it replaces human screening or is "validated". It is a tested prototype with one evaluation.
- Do not say it searches conferences, calls for papers or pushes to Zotero. Those parts are not built.
- Do not say it is production-ready, scheduled or published. It has a manual trigger.
- Do not say "free" without "on Groq's free tier, rate limited". Paid costs were not measured.
- Do not describe full-text analysis. It reads title and abstract only.
- Do not invent user numbers, time saved, or testimonials. None exist.

## Suggested page structure
1. Title, one-line pitch, status badge ("prototype, evaluated on one review").
2. The problem (two sentences from README "The problem").
3. Two ways to use it (use-case table above), with the architecture diagram (Mermaid in `README.md`).
4. How it keeps AI cost under control (token controls table).
5. What was measured, including the missed target and the finding (use "What the results mean").
6. Sample output (use `sample-output/prisma-counts.json` and `extraction-table.sample.csv`).
7. Limitations and what comes next (README "Limitations", "Status and roadmap").
8. Link to the repo and `workflow.json`.

## Assets
Available: `workflow.json`, Mermaid diagram in `README.md`, sample inputs and outputs, `eval.md`.
Missing: a canvas screenshot (`screenshot.png`), a drawn diagram image, a demo video. Do not reference them as if they exist.

## Tone
Plain, specific, first person singular or neutral. No hype words. Numbers always come with their caveat. British or Indian English spelling is fine; keep the author's own spelling of "normalise/normalize" consistent within a page.
