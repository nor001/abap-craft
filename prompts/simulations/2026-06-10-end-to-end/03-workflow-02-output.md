# Workflow 02 Output (Simulated)

## 1) German titles

- Wie ich Architectural Drift in SAP PM mit klaren Verantwortungsnamen gestoppt habe
- Warum ich API und CLIENT Verantwortung in ABAP strikt getrennt habe

Selected: Wie ich Architectural Drift in SAP PM mit klaren Verantwortungsnamen gestoppt habe

## 2) Spanish titles

- Como detuve architectural drift en SAP PM con nombres de responsabilidad
- Por que separe API y CLIENT para reducir regresiones en ABAP

Selected: Como detuve architectural drift en SAP PM con nombres de responsabilidad

## 3) German front matter draft

```yaml
---
layout: article
title: "Wie ich Architectural Drift in SAP PM mit klaren Verantwortungsnamen gestoppt habe"
date: 2026-06-10 00:00:00 +0000
lang: de
categories: [architecture]
description: "Wie eine ABAP-Verantwortungstaxonomie Grenzverletzungen sichtbar machte, bevor sie produktiv wurden."
back_label: "Zuruck zu ABAP Keyflow"
discuss_label: "Diesen Artikel diskutieren"
comments_intro: "Kommentare laufen uber GitHub Discussions."
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

## 4) Spanish front matter draft

```yaml
---
layout: article
title: "Como detuve architectural drift en SAP PM con nombres de responsabilidad"
date: 2026-06-10 00:00:00 +0000
lang: es
categories: [architecture]
description: "Como una taxonomia de responsabilidades en ABAP hizo visibles las violaciones de limite antes de produccion."
back_label: "Volver a ABAP Keyflow"
discuss_label: "Comenta este articulo"
comments_intro: "Los comentarios usan GitHub Discussions."
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

## 5) German article body (short simulation excerpt)

Beispiele verwenden generische Namen ZXX_*, um produktive Systeme zu schutzen.

Das Problem war nicht ABAP-Syntaxqualitat. Das Problem war unsichtbare Ownership zwischen API, CLIENT und SERVICE. Mit klarer Verantwortungstaxonomie wurden Grenzverletzungen schon im Design sichtbar.

## 6) Spanish article body (short simulation excerpt)

Los ejemplos usan nombres genericos ZXX_* para proteger sistemas productivos.

El problema no era la sintaxis ABAP. El problema era la propiedad difusa entre API, CLIENT y SERVICE. Con una taxonomia clara, las violaciones de limite aparecieron en diseno antes del merge.

## 7) Consistency report

- Argument parity: PASS
- Terminology parity: PASS
- Risk flags: NONE
