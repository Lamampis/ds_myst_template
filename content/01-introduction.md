# Introduction to MyST

MyST [@mystdocs] (Markedly Structured Text) Markdown is a powerful, open-source extension of standard Markdown, used for technical and scientific publishing. It enables users to produce complex, publication-ready documents, such as interactive websites, books, reports, and theses while preserving the simplicity and readability of Markdown's text editing. With the use templates, MyST seamlessly transforms intuitive Markdown into polished LaTeX-quality PDFs, allowing writers to prioritize content over formatting intricacies.

```{figure} https://mystmd.org/build/_assets/logo-wide-AK6GY6DB.svg
:label: MyST Logo
:width: 20%

MyST Logo
```

## Key Features of MyST Markdown

MyST elevates Markdown with specialized tools for academic and technical work:

- Scientific Layouts: Native support for citations, auto-numbered cross-references, LaTeX-powered equations (via MathJax or direct parsing), and captioned figures/tables.

- Extensible Syntax: Block-level directives (e.g., {admonition} Note for callouts, {tab-set} for comparisons) and inline roles (e.g., {ref}fig:myst-logo`` for links), inspired by reStructuredText but Markdown-friendly.

- Multi-Format Outputs: Write once, export to PDFs, DOCX, Jupyter Notebooks, or interactive HTML sites with Jupyter Book.

- Many quality community templates to chose from for any need.

These features make MyST ideal for reproducible research, embedding executable code from Jupyter, and Git-based collaboration.

## Why Choose MyST?

MyST combines Markdown's easy of use with LaTeX's precision, eliminating the complex and error-prone compilation of raw .tex files. Authors edit lightweight markdown files with live preview, while MyST handles typesetting, numbering, and styling in the background, for a workflow that is several times faster than traditional LaTeX workflows. Unlike proprietary tools, it's free, multi-platform, and version-control friendly, perfect for multi-author theses.

## Thesis Goal

This thesis develops a MyST Markdown template tailored for theses in the Department of Digital Systems at the University of Thessaly (UTH)[@uthsite]. It provides a simple, multi-platform alternative to the standard Microsoft Word template, producing similar PDF outputs with enhanced reproducibility, faster editing, and easier collaboration.
