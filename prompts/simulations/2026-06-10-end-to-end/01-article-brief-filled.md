# Article Brief (Filled)

## Metadata

- Date: 2026-06-10
- Working title: Stopping Architectural Drift With ABAP Responsibility Labels
- Primary language: EN
- Target languages: DE, ES

## Context

- System context (anonymized): SAP PM custom layer integrating SYSTEM_A and SYSTEM_B through MIDDLEWARE.
- Team context: Rotating ABAP team with mixed seniority.
- Trigger event: Regressions increased after extensions in TX01 and TX02.

## Core architectural tradeoff

- Option A: Keep feature delivery speed with loosely named classes and local conventions.
- Option B: Introduce strict responsibility taxonomy (API, CLIENT, SERVICE, FACADE, EXT) and enforce boundaries.
- Decision taken: Option B.
- Why this mattered: The team needed architecture visibility before opening class internals.

## What was breaking

- Maintainability impact: New classes duplicated transport logic and domain logic.
- Debugging cost impact: Root cause analysis crossed too many classes.
- Onboarding/team rotation impact: New developers could not infer ownership quickly.
- Regression risk: Changes in integration edges produced unexpected side effects.

## Defended decisions (2-4)

1. Separate API contract classes from HTTP transport classes.
2. Disallow business decisions inside CLIENT classes.
3. Introduce EXT classes for extension points only.
4. Reject mixed-responsibility helper classes.

## Evidence

- Observed class inventory / boundary examples: 80+ classes with inconsistent suffixes and mixed concerns.
- Before state: Boundary violations only discovered in code review.
- After state: Naming exposed violations during design and PR discussion.

## Repeatable test or heuristic

- Rule: If class name and method behavior imply two owners, the class is wrong.
- How to apply: Review suffix, dependencies, and outbound calls before implementation.
- Failure signal: A class requires exceptions to naming rules to justify behavior.

## Data-protection check

- Potential sensitive identifiers found: None.
- Sanitized placeholders used: ZXX_*, SYSTEM_A, SYSTEM_B, MIDDLEWARE, TX01, TX02.

## Supporting material

- Optional snippets: pseudo inventory table and mapping examples.
- Optional diagrams: simple flow between API, CLIENT, SERVICE.
- Related ABAP Keyflow links: existing architectural drift article variants.
