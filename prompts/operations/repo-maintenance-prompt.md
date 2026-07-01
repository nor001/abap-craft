# Operations Prompt: Repo Maintenance

Last updated: 2026-06-10

Run this prompt weekly or monthly to keep ABAP Keyflow healthy.

## Prompt

Audit this repository for AI-oriented editorial and publishing consistency.

Check the following areas:

1. Prompt quality
- Identify outdated prompts.
- Identify duplicated or conflicting constraints.
- Suggest minimal edits for clarity and maintainability.

2. Content consistency
- Verify EN/DE/ES parity for strategic articles.
- Flag semantic drift in architectural claims.
- Flag inconsistent terminology around ABAP/SAP integration boundaries.

3. Publication integrity
- Verify canonical routes and redirect integrity.
- Verify metadata quality (description, OG, Twitter).
- Verify comments labels and intro localization.

4. Safety and compliance
- Flag possible production-detail leaks.
- Flag non-anonymized identifiers.

5. Action plan
- Provide prioritized fixes as P0/P1/P2.
- Provide exact files to edit.
- Provide concise patch suggestions.

## Output format

1. Executive summary (max 8 lines)
2. Findings table (severity, file, issue, recommendation)
3. Proposed patch snippets
4. Follow-up checklist
