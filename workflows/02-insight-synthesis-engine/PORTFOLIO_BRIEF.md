# Portfolio brief: Insight Synthesis Engine

**Type:** Workflow

For the person or AI agent writing the portfolio page for this project. Everything below is checked against the files in this folder. Do not add claims that are not here.

## One-line pitch
An n8n workflow behind a one-page form where a researcher pastes interview transcripts, blogs, notes and web links, and gets back themes and insights with the exact quotes behind them, with participant names hidden before any AI sees the text.

## Who made it and why
- Author: Yash Bhagat, a design researcher.
- Built with Claude Code (an AI coding assistant) through n8n's built-in MCP server, with the author directing and reviewing. Say so if the page describes how it was built.
- It extends the author's position: a researcher who automates research operations, with a human verifying every judgement.

## Verified facts
| Fact | Evidence |
|---|---|
| 41 nodes plus 6 sticky notes, 5 Code nodes | `workflow.json` |
| Runs on n8n 2.45.6 self-hosted in Docker | `eval.md` |
| Input is a form; no node or JSON editing needed | `workflow.json`, `sample-output/form-page.jpg` |
| AI: Groq `openai/gpt-oss-120b`, free tier | `workflow.json` |
| Sample run: 40 pieces, 10 or 11 AI calls, 14,228 to 15,980 tokens, about 4 to 5 minutes | `eval.md` |
| Five repeat runs placed 14 to 29 of 40 pieces, in 4 or 5 themes | `eval.md` |
| 20 stress tests are recorded | `eval.md` |
| Stress testing found and fixed name-hiding gaps, silent text loss, wrong quote attribution and silent failures | `eval.md` |
| The exported `workflow.json` imported fresh and ran end to end with a Groq credential selected | `eval.md`, execution 43 |

## Story to tell
1. The first version needed the user to edit JSON inside a node. The stress test showed that was fragile and that several failures looked like success.
2. The rebuild removed whole classes of failure instead of patching them: a form replaced the JSON, ids became automatic, and each stage got a check with a plain message.
3. The test of a privacy feature found real gaps. Names in Hindi and with accents were not hidden in the first build, and they are now.

## Claims you may make
- It takes transcripts, pasted text and web links together.
- It hides listed names, emails and common phone formats before any AI call.
- Quotes are copied from the source by code, so the AI cannot reword them.
- Each insight shows its quotes, a stated limit and any flags. A theme backed by one type of source is flagged.
- Every stage ends in a check, and a failure shows a plain message on the form.
- It keeps AI use inside a token budget and says how much text was left out.
- It was stress tested with hostile input, and the results are published in `eval.md`.

## Claims you must NOT make
- Do not say it is accurate, validated, or matches human coding. It was never compared with human coding.
- Do not say it was tested on real participants or real interview data. All interview text was made up.
- Do not say it works at scale. It was tested on small samples, 40 pieces per run.
- Do not say it fully anonymises data. It hides listed names, emails and common phone formats only.
- Do not say data stays on the machine. Anonymised text goes to Groq.
- Do not say it replaces a researcher. A human checks every insight.
- Do not say it reads PDFs or uploaded files. Text is pasted, or fetched from web links.
- Do not say "free" without "on Groq's free tier, rate limited". Paid costs were not measured.
- Do not say it is deployed publicly. It runs on the author's local n8n.
- Do not invent user numbers, time saved or testimonials. None exist.

## Suggested page structure
1. Title, one-line pitch, status badge ("prototype, tested on small synthetic samples").
2. The problem (from README "The problem").
3. How it works, with `form-page.jpg`, the Mermaid diagram and `report-page.jpg`.
4. Design rules: quotes never reworded, names hidden first, a check after every stage.
5. What the stress test found (use "Story to tell", and the table in `eval.md`).
6. Honest results: the 14 to 29 spread, and that accuracy was not measured.
7. Limitations and what comes next (README).
8. Link to the repo and `workflow.json`.

## Assets
Available: `sample-output/form-page.jpg`, `sample-output/report-page.jpg` (from run 34), `sample-output/report.html`, the Mermaid diagram in `README.md`, sample inputs and outputs, `eval.md`.
Missing: a screenshot of the n8n canvas, a demo video. Do not reference them as if they exist.

## Tone
Plain, specific, first person singular or neutral. No hype words. Numbers always come with their caveat.
