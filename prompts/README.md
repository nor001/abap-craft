# ABAP Keyflow AI Prompt Infrastructure

This folder is the operating system for AI-assisted writing and publishing in ABAP Keyflow.

Use this order in normal operations:

1. `system/abap-keyflow-system-prompt.md`
2. `workflows/01-article-from-raw-notes.md`
3. `workflows/02-translation-sync.md`
4. `workflows/03-jekyll-publish-and-redirects.md`
5. `checklists/pre-publish-checklist.md`
6. `checklists/post-publish-checklist.md`
7. `operations/repo-maintenance-prompt.md` (weekly or monthly)

## Structure

- `system/`: repo-wide behavior and quality constraints for AI agents
- `workflows/`: end-to-end execution prompts
- `templates/`: reusable input/output structures
- `checklists/`: release-quality gates
- `operations/`: ongoing maintenance prompts

## Prompt versioning rules

- Keep prompts in plain Markdown.
- Keep each prompt single-purpose.
- If a prompt changes behavior, update `Last updated` and add a short changelog line.
- Do not delete old constraints silently; mark them as deprecated.

## Minimal runbook

1. Paste the `system` prompt in the AI session first.
2. Provide article input with `templates/article-brief-template.md`.
3. Run workflow 01 to generate the English source article.
4. Run workflow 02 for German and Spanish alignment.
5. Run workflow 03 to prepare publication files.
6. Validate with pre and post publish checklists.
