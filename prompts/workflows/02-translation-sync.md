# Workflow 02: Translation And Argument Sync

Last updated: 2026-06-10

## Goal

Create German and Spanish versions that preserve the same architecture argument as the English source.

## Inputs required

- Approved English source article
- Existing front matter draft
- Language-specific style constraints (if any)

## Prompt

You are adapting an ABAP Keyflow article from English into German and Spanish.

Rules:

- Preserve argument structure and technical claims.
- Do not add new architecture patterns.
- Keep SAP/ABAP technical terms standard and stable.
- Keep examples anonymized and consistent across languages.
- Adapt idiomatic phrasing while preserving meaning.

Return output in this exact order:

1. German title options (2) + selected title
2. Spanish title options (2) + selected title
3. German front matter draft
4. Spanish front matter draft
5. German article body
6. Spanish article body
7. Translation consistency report with:
   - argument parity
   - terminology parity
   - risk flags

## Acceptance criteria

- No semantic drift across languages.
- No conflicting claims between variants.
- `translations` metadata block points correctly among EN/DE/ES routes.
