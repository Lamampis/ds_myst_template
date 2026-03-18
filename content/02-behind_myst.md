# Technologies Powering MyST Markdown

To appreciate MyST's effectiveness, it's essential to explore its foundational technologies: Markdown and LaTeX. These form the backbone of MyST's hybrid approach, combining simplicity with professional-grade output.

## Markdown

Markdown is a lightweight markup language created by John Gruber in 2004 to simplify web writing with plain-text syntax that's both human-readable and convertible to HTML. It uses intuitive symbols for formatting: # for headings, *italic* or **bold** for emphasis, - or * for lists, and [text](URL) for links. 

MyST adheres to the CommonMark standard for consistency, while supporting popular flavors like GitHub Flavored Markdown (GFM) (tables, strikethrough, task lists) and Pandoc Markdown (footnotes, citations). These extensions make Markdown versatile for docs, blogs, and notes.

*Popular Editors:*

- Typora: Live WYSIWYG previews with seamless export.

- Obsidian: Linked notes and knowledge graphs via plugins.

- VS Code: Extensions for linting, previews, and Git integration.

- MarkText or Zettlr: Minimalist, distraction-free writing.

## LaTeX

LaTeX is a high-level typesetting system developed by Leslie Lamport in 1985 over Donald Knuth's TeX engine (1978), optimized for professional documents with math, technical diagrams, and structured content like theses.

```{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/9/92/LaTeX_logo.svg/250px-LaTeX_logo.svg.png
:label: LaTeX
:width: 20%

LaTeX Logo
```

Authors write .tex files and specify every detail, resulting in pixel-perfect PDFs, automating typography like kerning, ligatures, and hyphenation after compilation.

Unlike WYSIWYG editors, it's "What You See Is What You Mean," prioritizing semantics.

Key Strengths for Theses:

- Mathematics: Unrivaled rendering via amsmath (e.g., matrices, integrals: ∫abf(x) dx∫abf(x)dx).

- Automation: Dynamic tables of contents, numbered lists, bibliographies with BibTex

- Reproducibility: Single-command builds ensure identical outputs across machines.

Limitations: Steep learning curve, verbose syntax, slow compiles for large files (minutes vs. MyST's seconds), and difficult to debug error messages.

LaTeX remains the gold standard for STEM publishing (IEEE, arXiv), but MyST streamlines it for Markdown users.
