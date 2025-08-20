---

marp: true
math: katex
paginate: true
size: 16:9
headingDivider: 2

# Use the custom theme defined below

theme: iitm-docs
header: "Product Docs – v1.0"
footer: "Contact: [23f2000485@ds.study.iitm.ac.in](mailto:23f2000485@ds.study.iitm.ac.in)  •  © 2025 Your Company"
------------------------------------------------------------------------------------------------------------------

<!--
This Marp deck demonstrates: custom theme, page numbers, background image,
custom styling via directives, math, and your email visible on slides.
-->

<style>
/* --- Custom theme specification for Marp ------------------------------ */
/* Inherit from the default Marp theme and override styles */
@import 'default';
@theme iitm-docs {
  :root {
    --bg: #0b1220;
    --fg: #eef2ff;
    --accent: #60a5fa;
    --muted: #94a3b8;
  }
  section {
    background: var(--bg);
    color: var(--fg);
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
  }
  h1, h2, h3 { color: var(--fg); }
  a { color: var(--accent); }
  code, pre code { background: rgba(255,255,255,0.06); border-radius: 10px; }
  /* Page number position tweak */
  section::after {
    right: 28px;
    bottom: 22px;
    opacity: .7;
    font-size: .9rem;
  }
  /* Cards */
  .kpi {
    display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px;
  }
  .card {
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 18px; padding: 16px;
  }
}
</style>

<!-- _class: lead -->

# Product Documentation

**Modern, Maintainable, Multi‑format**

Email: [23f2000485@ds.study.iitm.ac.in](mailto:23f2000485@ds.study.iitm.ac.in)

*Technical Writer • Software Division*

---

## Agenda

1. Documentation principles
2. Version control & CI build
3. Content structure & theming
4. Export targets (HTML/PDF/PPTX)
5. Q\&A

---

## Background image example

<!--
Use a background image. You can replace with a local path in your repo
(e.g., ./assets/bg.jpg). For the live preview here, we point to a CDN.
-->

<!-- _backgroundImage: url('https://images.unsplash.com/photo-1520607162513-77705c0f0d4a?q=80&w=1600&auto=format&fit=crop') -->

<!-- _backgroundSize: cover -->

<!-- _color: #ffffff -->

<!-- _class: lead -->

### Clean & Readable Docs

**Version-controlled** sources that export to many formats.

---

## Maintainable in Git

* Keep docs as Markdown (`.md`) next to code
* Use **Marp CLI** in CI to produce HTML/PDF/PPTX
* PR reviews enforce consistency (linters, link check)
* Semantic sectioning with `##` headings

```bash
# Example CI step
marp slides.md --html --pdf --pptx --allow-local-files -o dist/
```

---

## Custom styling via directives

This slide uses local directives to override styling.

<!-- _color: #60a5fa -->

<!-- _paginate: true -->

<!-- _footer: "Contact: 23f2000485@ds.study.iitm.ac.in • iitm-docs theme" -->

* Per‑slide color, footer, background, classes
* Theme‑level tokens: `--bg`, `--fg`, `--accent`
* Utility classes like `.kpi` and `.card`

---

## KPIs (custom theme components)

<div class="kpi">
  <div class="card">
    <h3>Uptime</h3>
    <p><strong>99.97%</strong></p>
  </div>
  <div class="card">
    <h3>Latency p95</h3>
    <p><strong>118 ms</strong></p>
  </div>
  <div class="card">
    <h3>APIs</h3>
    <p><strong>142 endpoints</strong></p>
  </div>
</div>

---

## Math: Algorithmic complexity

Marp supports KaTeX math when `math: katex` is enabled.

* Merge sort: \$T(n) = 2,T(\tfrac{n}{2}) + O(n) \Rightarrow T(n) = O(n\log n)\$
* Binary search: \$T(n) = T(\tfrac{n}{2}) + O(1) \Rightarrow T(n) = O(\log n)\$
* Dynamic programming (grid): \$O(nm)\$

Block equation:

$$
T(n) = \sum_{i=0}^{\lfloor \log_2 n \rfloor} \frac{n}{2^i} = 2n - 1 = O(n)
$$

---

## Code sample (fenced)

```ts
// Typed config example
export interface BuildTargets {
  html: boolean
  pdf: boolean
  pptx: boolean
}

export const targets: BuildTargets = { html: true, pdf: true, pptx: true }
```

---

## Exporting & Hosting

* **HTML** for web docs (host via GitHub Pages)
* **PDF** for offline distribution
* **PPTX** for stakeholder slides

```bash
# GitHub Pages (example)
git add slides.md
git commit -m "docs: product docs deck"
git push origin main
```

> Pages will serve `index.html`. Use `marp slides.md -o index.html` in CI.

---

## Contact

Questions? Reach out at **[23f2000485@ds.study.iitm.ac.in](mailto:23f2000485@ds.study.iitm.ac.in)**

Thank you!
