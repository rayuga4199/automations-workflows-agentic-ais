# Portfolio brief: [AI Agent] Research Writer

**Type:** AI agent

For the person or AI agent writing the portfolio page. Everything here is checked against this folder. Do not add claims that are not here.

## One-line pitch
An AI agent that checks a researcher's draft against their own quote ledger, verifies references and polishes their sentences, and refuses to write content or invent a citation.

## Who made it
Author: Yash Bhagat, a design researcher. Built with Claude Code (an AI coding assistant) in n8n, with the author directing and reviewing. Say so if the page describes how it was built.

## Verified facts
| Fact | Evidence |
|---|---|
| One n8n Agent with three read-only tools | `agent-config.json`, `tools-helper.json` |
| Only a person can add to the ledger, through a form | `add-quote-helper.json` |
| Seeded test: 20 of 20 unsupported claims caught and 10 of 10 supported claims matched, on 30 sentences and 8 ledger quotes | `eval.md`, `sample-output/` |
| It refused to write a paragraph, and refused to add a citation while polishing | `eval.md` |
| A fake reference was reported as not found, and a real DOI was verified | `eval.md` |

## Story to tell
1. Academic AI tools can invent references. This design removes the chance: the agent can read the ledger but cannot write to it, and references are checked against OpenAlex.
2. The target was 18 of 20 seeded claims with no bad citations.
3. Testing found a tool bug that hid the ledger, and a weak spot with words like "eliminates". Both were fixed and retested.

## Claims you may make
- It marks each sentence as supported, unsupported or not a claim, and names the ledger entry.
- It never writes new content, by rule and in testing.
- The ledger is read-only to the agent.
- It separates a topic match from real support.

## Claims you must NOT make
- Do not say it is finished, published or in daily use. It is an unpublished draft.
- Do not say it finds papers or research gaps reliably. Those skills, and the Add Quote form, are untested.
- Do not say it resists all attacks. The attack test was not rerun on the final rules.
- Do not say the 30 of 30 proves real-world accuracy. The test draft was written by the builder, in batches of 10, against a very small ledger.
- Do not say it handles long drafts. A 30-sentence check timed out.
- Do not say it reads PDFs or full papers. It reads the quotes you add and search abstracts.
- Do not invent user numbers, time saved or testimonials. None exist.

## Suggested page structure
1. Title, pitch, status badge ("unpublished draft, seeded test passed").
2. The problem: invented citations.
3. How it works (Mermaid diagram in `README.md`).
4. The seeded test and what it found (`eval.md`).
5. Limitations and what is left.

## Assets
Available: the Mermaid diagram, `sample-input/`, `sample-output/`, `eval.md`, and in `screenshots/` the agent page and both helper canvases.
Missing: a screenshot of a live conversation, a demo video. Do not reference them as if they exist.

## Tone
Plain, specific, first person singular or neutral. No hype words. Numbers always come with their caveat.
