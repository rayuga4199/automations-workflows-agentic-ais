# Sanitization and secret scan

Run this before every push and again, on full history, before the repo goes public. Public API keys get abused within hours.

## Before committing an n8n export
- [ ] No API keys, tokens or passwords anywhere in `workflow.json`, READMEs or samples.
- [ ] Credential blocks reduced to a placeholder name. Remove real credential IDs from every node's `credentials` field.
- [ ] Webhook URLs and webhook paths replaced with placeholders. Production webhook IDs stripped.
- [ ] Personal IDs removed or replaced: Zotero user ID, Google Doc, Drive and Sheet IDs, email addresses, `instanceId` under `meta`.
- [ ] `pinData` removed from the export (it can hold real execution data).
- [ ] Participant data anonymized before it enters `sample-input/`. Names, places, employers, voices.
- [ ] Sample papers are open-access only. No copyrighted PDFs.
- [ ] The workflow runs on the bundled sample data with credentials as the only edit.

## Secret scan (gitleaks)
Tool: [gitleaks](https://github.com/gitleaks/gitleaks). Current commands are `git`, `dir` and `stdin`. `detect` and `protect` are deprecated since v8.19.0. Verified against the official README on 2026-10-27. Install: `winget install Gitleaks.Gitleaks` (Windows), or the Docker image `ghcr.io/gitleaks/gitleaks`.

Scan the full history (all refs). Run this before going public:

```bash
gitleaks git --log-opts="--all" --redact -v .
```

Scan the working tree, including untracked files:

```bash
gitleaks dir --redact -v .
```

Scan only staged changes (this is what the pre-commit hook runs):

```bash
gitleaks git --pre-commit --staged --redact -v .
```

Enable the bundled pre-commit hook once per clone:

```bash
git config core.hooksPath .githooks
```

Exit code 0 means no leaks. Non-zero means a finding: rotate the secret first, then remove it from history. Deleting the line in a later commit does not remove it from history.

## Scan log
| Date | Command | Result |
|---|---|---|
| 2026-10-29 | `gitleaks dir --redact .` before first commit | no leaks found |
