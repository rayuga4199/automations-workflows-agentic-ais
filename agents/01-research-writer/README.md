# [AI Agent] Research Writer

**Type:** AI agent

One n8n Agent that helps a researcher check a draft against a quote ledger, verify references, find papers and polish their own sentences. It never writes content for them and never invents a reference.

**Status (2026-10-30):** unpublished draft in n8n, not finished. Results are in [eval.md](eval.md).

## How it works
- **Quote ledger:** the n8n data table `research_ledger`. Only a person can add to it, through the Add Quote form (`add-quote-helper.json`). The agent can only read it.
- **Tools (`tools-helper.json`):** read the ledger, search OpenAlex, verify a reference. Answers come from the database or ledger, not the AI.
- **Model:** Groq `openai/gpt-oss-20b`, free tier, 200,000 tokens a day shared across Groq steps.

## Limitations
- Check about 10 sentences at a time. A 30-sentence check timed out.
- The sample ledger holds only 8 quotes from abstracts.
- The agent's own settings live in n8n and are not exported here.
