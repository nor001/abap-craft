# Workflow 01: Article From Raw Notes

Last updated: 2026-06-10

## Goal

Convert anonymized SAP/ABAP experience into a publication-ready English architecture article.

## Inputs required

- Completed `templates/article-brief-template.md`
- Optional technical notes and decision logs
- Existing related article links in this repo (if any)

## Prompt

You are writing an ABAP Keyflow article from real architecture experience.

Follow these rules:

- Focus on the core tradeoff, not the surface topic.
- Keep claims evidence-based from the provided input.
- Keep production-safe placeholders only (ZXX_*, SYSTEM_A, SYSTEM_B, MIDDLEWARE, TX01, TX02).
- Use a senior practitioner voice, not tutorial voice.

Return output in this exact order:

1. Proposed title options (3)
2. Final title selected (1)
3. Front matter draft using `templates/post-front-matter-template.md`
4. Full article body (1000-1500 words target)
5. LinkedIn variants (3)
6. dev.to tags (2)
7. Risk flag sentence (production-detail check)

## Acceptance criteria

- Architectural decision is explicit.
- At least two defended tradeoffs are present.
- Scale-level implication is concrete.
- Final lesson is concise and memorable.
- No production-identifying details.
