# Evaluation: [Workflow] Insight Synthesis Engine

All tests ran on 2026-10-30 on n8n 2.45.6 (self-hosted, Docker) with Groq `openai/gpt-oss-120b` on the free tier. Execution numbers are from the author's local n8n instance.

**What this file shows:** the workflow runs, handles bad input and tells the user what went wrong. **What it does not show:** that the themes are correct. Output was never compared with human coding, so there is no accuracy figure.

## Test data
Three made-up interview transcripts, one made-up blog post and one made-up field note, about a mixed reality navigation companion, plus the Wikipedia page on wayfinding. The form runs also included one dead link and one line that is not a link. The files are in `sample-input/`.

## Repeat runs on the sample
Each row is one full run. All used 40 text pieces. Runs 21 to 33 used the earlier pasted-JSON input. Runs 34 and 42 used the form.

| Execution | Pieces placed in a theme | Themes | AI calls | Tokens (measured) | Minutes |
|---|---|---|---|---|---|
| 21 | 17 | 5 | 11 | 15,980 | 4.5 |
| 32 | 15 | 4 | 10 | 14,228 | 4.0 |
| 33 | 29 | 4 | 10 | 14,549 | 4.0 |
| 34 | 14 | 4 | 10 | 14,537 | 4.1 |
| 42 | 17 | 5 | 11 | 15,697 | 4.6 |

Execution 32's own report showed 6 AI calls because of a counting bug fixed before execution 33. The table shows the true count.

**Reading:** the pipeline is steady, but the analysis is not. The same material gave 14 to 29 placed pieces, which is a wide spread. Part of it is expected, since most unplaced pieces came from the general Wikipedia page. It still means one run should be treated as a first draft.

## Stress tests
Hostile runs 23 and 24, and failure runs 25 to 31, used a temporary copy of the workflow. Runs 34 to 42 used the published form. The form tests were sent directly to the form URL, because the test browser blocks form submissions.

| Test | First result | After the fix |
|---|---|---|
| Hindi and accented names (run 23) | Not hidden, or partly hidden | Hidden, including José in capitals (runs 24, 38) |
| Names with an apostrophe or dots (run 23) | Not hidden | Hidden (runs 24, 38) |
| Text with "A.B." style abbreviations (run 23) | Text silently dropped | No text lost (run 24) |
| Two sources with the same id (run 23) | A quote showed the wrong text | Ids are now automatic, so this cannot occur |
| One sentence of over 1,300 characters (run 23) | One huge piece, ignoring the limit | Split, longest piece 180 characters (runs 24, 37) |
| Invalid JSON input (run 25) | Green run with no report | JSON input removed; the form has no such failure |
| Empty form (run 35) | Not applicable | Plain message on the form |
| Only very short text (run 36) | No report, same path as run 25 | Plain message on the form |
| Real Groq rate limit, no pacing, right after other runs (run 30) | Green run with no report | Plain message on the form (simulated in run 40) |
| Theme AI broken on purpose (run 39) | Not applicable | Plain message on the form |
| Placement AI broken on purpose (run 40) | Not applicable | Plain message on the form |
| Insight AI broken on purpose (run 41) | Not applicable | Report still shown, with the insight flagged for hand writing |
| Dead link (runs 22, 34) | Run completed | Run completed, link named in the report |
| Unreachable host, non-HTML page (run 37) | Run completed | Both named in the report |
| `javascript:` and `file:` links (run 37) | Not applicable | Skipped, and counted in the report |
| Prompt injection in a source (runs 23, 24, 37) | AI ignored it | No theme or insight followed it |
| `<script>` and `<img onerror>` in a source (run 37) | Not applicable | Escaped on the report page |
| `{{ }}`, `{foo}`, `${x}`, emoji, German, Chinese (runs 24, 37) | Run completed | Run completed |
| Very small budget, 2,000 tokens (run 30) | Capped at 4 pieces | Cap logic unchanged since |
| No pacing at all (run 29) | Passed in 22 seconds, 14 pieces | Not repeated |

One privacy result looked like a failure and was not. In run 37, two names reached the AI because the test shell damaged them before sending. The value received was visibly corrupted. Run 38 repeated the test with correct UTF-8 and every name was hidden. A real browser sends UTF-8.

## Fresh import
Execution 43: the exact `workflow.json` in this folder was imported into n8n as a new workflow. The only edits were selecting the Groq credential and using another form path, because the live workflow already held the default one. It ran end to end through its own form, with the sample transcripts as input. The test copy was then deleted.

## Not tested
- A real person clicking through the form in a normal browser. The form was submitted over HTTP and the report page was viewed in a browser, but the test browser blocks the submit step.
- A run where only some AI batches fail. All-batches failure is tested; the partial warning is not.
- Large volumes, or more than one person using the form at once.
- Real interview data.
- Agreement with human coding.
