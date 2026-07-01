# Workflow 03: Jekyll Publish And Redirects

Last updated: 2026-06-10

## Goal

Transform approved article content into repository-ready Jekyll files and optional legacy redirects.

## Inputs required

- Final EN/DE/ES content
- Publication date (YYYY-MM-DD)
- Canonical slugs for each language
- Decision on whether legacy redirects are required

## Prompt

You are preparing publication assets for ABAP Keyflow.

Tasks:

1. Generate canonical Jekyll post filenames for EN/DE/ES.
2. Generate complete front matter for each post.
3. Ensure metadata fields align with `_layouts/article.html`.
4. Generate redirect page front matter files under `posts/` when required.
5. Provide a final file manifest and a short validation checklist.

Rules:

- Use lowercase ASCII slugs with hyphens.
- Keep language code in filename (`en-`, `de-`, `es-`).
- Preserve translation links among all 3 versions.
- Use `layout: redirect` and `redirect_to` for legacy pages.

Return output in this exact order:

1. File manifest
2. EN post content
3. DE post content
4. ES post content
5. Redirect file contents (if required)
6. Final validation report

## Acceptance criteria

- Every generated file has valid front matter.
- Canonical and redirect URLs are internally consistent.
- Output is directly committable to this repository.
