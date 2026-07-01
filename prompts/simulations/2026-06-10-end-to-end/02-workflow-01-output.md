# Workflow 01 Output (Simulated)

## 1) Proposed title options

1. How I Stopped Architectural Drift in SAP PM by Naming Responsibility First
2. Why I Split API and CLIENT Ownership Before Touching Another ABAP Class
3. How Responsibility Labels Reduced Regression Risk in a Large ABAP Codebase

## 2) Final title selected

How I Stopped Architectural Drift in SAP PM by Naming Responsibility First

## 3) Front matter draft

```yaml
---
layout: article
title: "How I Stopped Architectural Drift in SAP PM by Naming Responsibility First"
date: 2026-06-10 00:00:00 +0000
lang: en
categories: [architecture]
description: "How I used an ABAP responsibility taxonomy to expose boundary violations before they reached production in a SAP PM custom landscape."
og_description: "An architecture decision story on separating API, CLIENT, SERVICE, FACADE, and EXT responsibilities in ABAP."
twitter_description: "A practical ABAP architecture pattern to stop drift and reduce regressions in SAP PM custom code."
back_label: "Back to ABAP Keyflow"
discuss_label: "Discuss this article"
comments_intro: "Comments are powered by GitHub Discussions."
translations:
  - lang: en
    label: English
    url: /architecture/2026/06/10/en-how-i-stopped-architectural-drift-by-naming-responsibility-first/
  - lang: de
    label: Deutsch
    url: /architecture/2026/06/10/de-wie-ich-architectural-drift-mit-verantwortungsnamen-gestoppt-habe/
  - lang: es
    label: Espanol
    url: /architecture/2026/06/10/es-como-detuve-architectural-drift-con-nombres-de-responsabilidad/
---
```

## 4) Full article body

Examples use generic names ZXX_* to protect production systems.

For years I saw the same pattern in SAP PM custom landscapes. A project started clean. The first integration was understandable. Then the second and third arrived, and the class inventory grew faster than the team's shared architecture language.

The breaking point was never syntax quality. The breaking point was ownership ambiguity.

When a class said it was an API but also did transport retries, payload normalization, and business fallback logic, nobody could reason about boundaries with confidence. Code review became archaeology.

The system context was familiar: SYSTEM_A and SYSTEM_B exchanging data through MIDDLEWARE, with local enhancements around TX01 and TX02. The codebase had 80+ classes and many of them looked clean in isolation. The problem was the interaction model.

The decision I had to defend was simple to describe and hard to implement: enforce a responsibility taxonomy and treat naming as an architectural control surface, not a cosmetic choice.

I standardized five ownership labels:

- API: inbound or outbound business contract ownership
- CLIENT: transport and protocol ownership
- SERVICE: business orchestration ownership
- FACADE: stable aggregation boundary for callers
- EXT: explicit extension point ownership

That looks obvious in hindsight, but at the time the team resisted for good reasons. Delivery pressure made mixed classes attractive because one file solved one urgent ticket. Refactoring into clear ownership looked slower at sprint scale.

The first defended decision was separating API from CLIENT even when the same developer owned both. If one class owns both contract semantics and HTTP mechanics, any change in payload behavior risks transport regressions and vice versa. Splitting those concerns reduced hidden coupling and made test intent obvious.

The second defended decision was banning business decisions from CLIENT classes. CLIENT classes can transform technical errors and retry transport safely, but they cannot decide business fallback rules. Once they do, transport failures become domain behavior by accident.

The third defended decision was reserving EXT for extension points only. In the old model, EXT became a miscellaneous zone where any urgent adaptation landed. That destroyed predictability. In the new model, EXT classes were reviewed with one question: does this preserve the stable contract and isolate customer-specific variation?

The fourth defended decision was rejecting helper classes that carried two owners. Helpers sounded neutral, but most became dependency magnets. If a helper touched both integration transport and business workflow, it was not a helper. It was unowned architecture.

At scale, the impact was immediate in design conversations. Before opening implementation details, we could inspect class inventory and see boundary health. Violations became visible from names and dependency direction.

A simplified before-and-after view made this obvious.

Before:

- ZXX_CL_SYNC_HANDLER
- ZXX_CL_SYNC_UTIL
- ZXX_CL_PM_ENGINE
- ZXX_CL_HTTP_WRAPPER
- ZXX_CL_EXT_RULES

After:

- ZXX_CL_ORDER_API
- ZXX_CL_ORDER_CLIENT
- ZXX_CL_ORDER_SERVICE
- ZXX_CL_PM_FACADE
- ZXX_CL_ORDER_EXT

The old names reflected activity. The new names reflected ownership.

That shift changed review dynamics. Instead of discussing style first, we discussed architecture first. If a proposed class name implied SERVICE but dependencies showed direct HTTP behavior, the mismatch was a design defect before coding.

The heuristic we adopted is still the fastest quality gate I know for this context:

If class name and method behavior imply two owners, the class is wrong.

Applying it is operationally simple:

1. Validate suffix and owner intent before implementation.
2. Review dependencies for owner violations.
3. Reject exceptions that require narrative justification.

The failure signal is clear: when a class needs special explanation to justify behavior outside its owner type, the boundary is already broken.

This approach did not eliminate all defects. It did something more valuable: it lowered the probability of invisible architecture decay during normal delivery pressure. Team rotation became less risky because responsibility was legible from structure.

In large ABAP landscapes, maintainability depends less on perfect code and more on visible ownership. Naming conventions become architecture when they make violations obvious before they are merged.

## 5) LinkedIn variants

I used to think architectural drift in ABAP happened because systems got old. In practice, it happened because class ownership became invisible. I introduced a responsibility taxonomy (API, CLIENT, SERVICE, FACADE, EXT) and made naming a design gate. The result was faster boundary discussions, cleaner reviews, and lower regression risk in SAP PM integrations.

A useful lesson from SAP PM custom work: code quality is not enough when ownership is ambiguous. We stopped mixing contract logic, transport logic, and orchestration in the same classes. Once names reflected responsibility, architectural violations became visible before implementation.

In integration-heavy ABAP codebases, delivery pressure pushes teams toward mixed classes that solve urgent tickets. I moved to strict ownership labels and rejected two-owner classes. That single rule improved maintainability and reduced hidden coupling more than any style guideline we had.

## 6) dev.to tags

#abap
#architecture

## 7) Risk flag

No production-detail risk detected.
