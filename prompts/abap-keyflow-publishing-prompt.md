# ABAP Keyflow Publishing Prompt

This is the public publishing prompt and style guide for **ABAP Keyflow**.

It documents how new ABAP Keyflow articles should be written, anonymized, translated, and published on the GitHub Pages site.

Website:

```text
https://nor001.github.io/ABAP_Keyflow/
```

Repository:

```text
nor001/ABAP_Keyflow
```

---

## Purpose

ABAP Keyflow is a technical blog about real ABAP/SAP architecture experience.

The goal is to publish articles that show practical senior-level thinking, especially around:

- ABAP architecture
- SAP PM custom development
- integration design
- maintainability
- architectural drift
- team rotation
- responsibility boundaries
- AI-assisted publishing and documentation

The blog should not feel like a beginner tutorial site. It should feel like practical architecture notes from someone who has maintained real SAP systems under delivery pressure.

---

## Article model

A strong ABAP Keyflow article usually follows this structure:

1. Strong title
2. Short data-protection note
3. Real-world context
4. The real problem
5. The architectural decision or pattern
6. Decisions that had to be defended
7. What it looks like at scale
8. Practical checklist or test
9. Final lesson
10. Comments section

Good topics are based on real architectural tension:

- architectural drift in SAP systems
- large ABAP class inventories
- unclear responsibility boundaries
- external integration complexity
- transaction extensions becoming unmaintainable
- separating API, CLIENT, SERVICE, FACADE, and EXT roles
- making architecture visible through naming
- using AI to turn SAP experience into reusable technical writing

---

## Data protection

Production details must be anonymized.

Do not publish real names of clients, systems, URLs, RFC destinations, payloads, tickets, colleagues, screenshots, or class names that identify a productive implementation.

Use generic names such as:

```text
ZXX_*
SYSTEM_A
SYSTEM_B
MIDDLEWARE
TX01
TX02
ORDER
NOTIFICATION
EQUIPMENT
FLOC
```

Every article should include a visible note near the top.

English:

```html
<p class="note">Examples use generic names <code>ZXX_*</code> to protect production systems.</p>
```

Spanish:

```html
<p class="note">Los ejemplos usan nombres genéricos <code>ZXX_*</code> para proteger sistemas productivos.</p>
```

German:

```html
<p class="note">Die Beispiele verwenden generische Namen wie <code>ZXX_*</code>, um produktive Systeme zu schützen.</p>
```

Recommended CSS:

```css
.note { color: #cbd5e1; font-style: italic; font-weight: 600; }
```

---

## Languages

Strategic articles should be published in three versions:

- English
- German
- Spanish

English is the main international version.
German supports European SAP positioning.
Spanish keeps the author's natural technical voice.

Use separate source files:

```text
_posts/YYYY-MM-DD-en-<slug>.md
_posts/YYYY-MM-DD-de-<slug>.md
_posts/YYYY-MM-DD-es-<slug>.md
```

The homepage should detect browser language and allow manual switching between EN, DE, and ES.

---

## Static site rules

ABAP Keyflow is intentionally simple.

Use:

- Jekyll posts in `_posts/` as the source of truth
- a Jekyll-rendered homepage in `index.html`
- inline CSS
- minimal JavaScript
- no frontend framework
- GitHub Pages as the only build layer

Legacy HTML files under `posts/` should exist only as redirects when old URLs must be preserved.

Main files:

```text
index.html
_posts/*.md
posts/en-*.html
posts/de-*.html
posts/es-*.html
prompts/abap-keyflow-publishing-prompt.md
```

---

## Visual style

Use the existing dark theme.

Core colors:

```css
background: #0f172a;
article/code background: #020617;
text: #e5e7eb;
paragraph text: #cbd5e1;
muted text: #94a3b8;
accent: #38bdf8;
border: #1f2937;
```

Article container:

```css
main { max-width: 900px; margin: 0 auto; padding: 44px 22px 80px; }
```

Article title:

```css
h1 { font-size: clamp(34px, 6vw, 62px); line-height: 1.05; }
```

Code blocks:

```css
pre {
  background: #020617;
  border: 1px solid #1f2937;
  border-radius: 14px;
  padding: 16px;
  overflow-x: auto;
}
code { color: #e0f2fe; }
```

---

## SEO and social sharing

Every article should include:

```html
<meta name="description" content="...">
<meta name="author" content="Norman Neri">
<meta property="og:title" content="...">
<meta property="og:description" content="...">
<meta property="og:type" content="article">
<meta property="og:url" content="https://nor001.github.io/ABAP_Keyflow/<localized-path>/<slug>/">
<meta name="twitter:card" content="summary">
<meta name="twitter:title" content="...">
<meta name="twitter:description" content="...">
```

Descriptions should be short, concrete, and architecture-focused.

Good:

```text
How I stopped architectural drift in a large SAP PM system using a class naming taxonomy that makes responsibility violations visible before they are committed.
```

Weak:

```text
A blog post about ABAP naming conventions.
```

---

## Comments

Use Giscus only on article pages, not on the homepage.

Current Giscus setup:

```text
repo: nor001/ABAP_Keyflow
repo-id: R_kgDOS0zSjg
category: General
category-id: DIC_kwDOS0zSjs4C-zHy
mapping: pathname
theme: preferred_color_scheme
```

Use language-specific section titles:

```text
English: Discuss this article
Spanish: Comenta este artículo
German: Diesen Artikel diskutieren
```

---

## Analytics

The site may use GoatCounter.

Analytics should stay private to the author.
Do not add a public visitor counter unless explicitly requested.
Preserve existing analytics scripts when editing pages.

---

## Slug rules

Use lowercase filenames, hyphens, and no accents.

Good:

```text
posts/es-como-evite-clases-abap-sin-responsabilidad.html
```

Bad:

```text
posts/es-cómo-evité-clases-abap-sin-responsabilidad.html
```

---

## Title strategy

Prefer strong, experience-based titles.

Good examples:

```text
How I stopped architectural drift in a large SAP PM system
How I separated integration logic from business logic in ABAP
Why I stopped using generic manager classes in SAP PM
The ABAP class boundary that saved our integration layer
How I made SAP PM extensions understandable for rotating teams
How I use AI to turn SAP architecture experience into reusable posts
```

Avoid weak titles:

```text
ABAP naming tutorial
How to name classes in ABAP
SAP PM clean code basics
```

---

## Publishing checklist

Before publishing a new article:

- [ ] Data is anonymized.
- [ ] Examples use `ZXX_*` or generic names.
- [ ] Protection note is visible.
- [ ] Article has metadata and OG tags.
- [ ] Article has Giscus comments in the correct language.
- [ ] Homepage links to the article in EN, DE, and ES.
- [ ] Language switcher still works.
- [ ] Existing analytics are preserved.
- [ ] HTML works as static GitHub Pages content.
- [ ] Tone is senior and architectural.

---

## Expected publishing result

A completed publishing action should report:

```text
Commit:
<sha>

Files:
- _posts/YYYY-MM-DD-en-...
- _posts/YYYY-MM-DD-de-...
- _posts/YYYY-MM-DD-es-...
- index.html

URLs:
- https://nor001.github.io/ABAP_Keyflow/architecture/...
- https://nor001.github.io/ABAP_Keyflow/architektur/...
- https://nor001.github.io/ABAP_Keyflow/arquitectura/...

Notes:
- data protection applied
- meta tags included
- Giscus included
- language selector updated
- legacy redirects preserved when needed
```
