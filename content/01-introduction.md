# Introduction

# Markup Languages
Markup languages play an important role in the creation, organization, and presentation of digital documents. Unlike plain text, they allow additional information to describe the structure, meaning, or presentation of content, enabling elements such as headings, paragraphs, tables, and references to be represented in a structured and machine-readable form. Their development has significantly influenced how digital information is authored, processed, exchanged, and published, particularly in areas such as web development, scientific publishing, and technical communication. Over time, markup languages have evolved from systems focused primarily on formatting toward approaches that emphasize structure, reusability, and the separation of content from presentation. This evolution has led to the development of systems such as LaTeX, Markdown, and its various extensions.

# Thesis Goal

The objective of this thesis is to develop a Thesis template made using {index}`MyST` Markdown tailored specifically for students of the Department of Digital Systems at the University of Thessaly (UTH)[@uthsite]. PDF is the output format that will be used. This proposed solution aims to serve as a practical and accessible alternative to the existing Microsoft Word template.

More specifically, this thesis seeks to:

* Provide a **simple and intuitive writing environment** based on Markdown.
* Ensure **high-quality PDF output** comparable to existing templates.
* Explain the **process of creating an adequate template** using MyST.
* Outline **important Markdown and MyST specific syntax**.
* Guide the user through the whole **process of writing an academin document** from start to finish.

By combining usability with professional typesetting capabilities, this template aspires to modernize the thesis-writing workflow and align it with contemporary tools and practices in academic publishing.

# Core Technologies

Before we go into MyST (Markedly Structured Text) [@mystdocs], it is important to examine the two foundational technologies upon which it is built: Markdown and LaTeX. These systems represent two different philosophies of document creation—simplicity and precision—and MyST successfully integrates both into a unified workflow. This hybrid approach enables authors to produce documents that are both easy to write and professionally formatted.

## Markdown
Markdown is a lightweight markup language created by John Gruber in 2004. Its primary goal was to simplify writing for the web by using plain-text syntax that is easy to read and write, while still being convertible into structured formats such as HTML.

The syntax of Markdown is intentionally minimal and intuitive. For example:

* `#` is used for headings
* `*italic*` and `**bold**` denote emphasis
* `-` or `*` create lists
* `[text](URL)` defines hyperlinks

This simplicity makes Markdown highly accessible, even for users with no prior experience in markup languages.


### Popular Markdown Editors

A variety of modern editors support Markdown and improve the writing experience:

* **Typora:** Provides a live preview ({abbr}`WYSIWYG (What you see is what you get)`-style), allowing users to see formatted text in real time
* **Obsidian:** Focuses on knowledge management through linked notes and graph visualization
* **Visual Studio Code:** Offers powerful extensions for linting, previewing, and {index}`version control` integration
* **MarkText** and **Zettlr:** Minimalist editors designed for distraction-free writing

These tools demonstrate the widespread adoption of Markdown across both casual and professional contexts.

## LaTeX

{index}`LaTeX` [@latexdocumentation] is a high-level typesetting system developed by Leslie Lamport in 1985, built on top of Donald Knuth’s TeX engine (introduced in 1978). It is specifically designed for producing high-quality technical and scientific documents, making it the de facto standard in many academic disciplines.

:::{glossary}
LaTeX
: A document preparation and typesetting system widely used for producing high-quality scientific and technical documents.
:::

```{figure} /content/images/latex_logo.png
:label: fig-latex-logo
:width: 20%

LaTeX Logo
```

Unlike Markdown, *{term}`LaTeX`* provides precise control over document structure and formatting. Authors write source files (`.tex`) that define both content and layout. These files are then compiled into output formats such as PDF, ensuring consistent and professional results.

LaTeX follows a “What You See Is What You Mean” paradigm, emphasizing logical structure over immediate visual representation. While this differs from WYSIWYG editors, it allows for superior consistency and automation.

### Key Strengths for Academic Writing

{index}`LaTeX` offers several advantages, particularly for theses and scientific publications:

* **Advanced Mathematics:**
  LaTeX excels at rendering complex mathematical expressions using packages such as `amsmath`. For example:
  $$ \int_a^b f(x),dx $$

* **Automation:**
  It automatically generates tables of contents, figure numbering, cross-references, and bibliographies (via BibTeX or BibLaTeX).

* **Typographic Quality:**
  LaTeX handles kerning, ligatures, spacing, and hyphenation with exceptional precision, producing publication-quality documents.

* **Reproducibility:**
  Documents can be compiled consistently across different systems, ensuring identical outputs with a single command.

### Limitations

Despite its strengths, LaTeX has several drawbacks:

* **Steep Learning Curve:**
  Beginners often struggle with its syntax and structure

* **Verbose Code:**
  Writing even simple documents can require extensive markup

* **Compilation Time:**
  Large documents may take significant time to compile

* **Error Debugging:**
  Error messages can be cryptic and difficult to interpret

# MyST Markdown

## What is MyST Markdown?
Markedly Structured Text Markdown, {index}`version control` for short, is an open-source project developed under the Project Jupyter[@jupyter] ecosystem designed specifically for scientific, academic, and technical communication. 

MyST builds upon the **CommonMark** specification, ensuring consistency and predictability across implementations. In addition, it supports widely used extensions such as:

* **GitHub Flavored Markdown (GFM):** Adds features like tables, task lists, and strikethrough text
* **Pandoc Markdown:** Introduces advanced capabilities such as citations, footnotes, and metadata handling

These extensions significantly enhance Markdown’s versatility, allowing it to be used not only for simple notes and blogs, but also for technical documentation and academic writing. 

It allows the user to export documents in multiple formats, including interactive HTML websites, Microsoft Word Files (.docx), or print-ready LaTeX and PDFs for books, reports and academic theses, while preserving the simplicity and readability of plain text editing. 

By leveraging structured templates and modern tooling, MyST seamlessly transforms intuitive Markdown content into professionally formatted outputs. This approach allows writers to focus primarily on content creation, rather than formatting details, significantly improving productivity and reducing friction in the writing process.

```{figure} /content/images/myst_logo.png
:label: mystmd-logo
:width: 20%

MyST Logo
```

## Key Features:
{index}`MyST` extends the capabilities of traditional Markdown by introducing advanced features tailored for academic and technical writing:

* **Unified Compilation to Multiple Layouts.** 
  The contents of the user's markdown files can be compiled into multiple different formats, including Websites, PDF/LaTeX, and Microsoft Word Documents.

* **Deep Configuration.** 
  Every detail can be configured to the user's liking through configuration files.

* **Scientific Layouts:**
  Native support for citations, automatically numbered cross-references, LaTeX-style mathematical expressions (via MathJax or direct parsing), and fully captioned figures and tables.

* **Extended Markdown Syntax:**
  MyST introduces block-level **directives** (e.g., `{admonition}` for callouts or `{tab-set}` for structured comparisons) and inline **roles** (e.g., `{ref}` for cross-referencing). These features are inspired by reStructuredText but adapted to remain intuitive for Markdown users.

* **Template Ecosystem:**
  A wide range of community-developed templates allows users to quickly adopt professional layouts suitable for reports, articles, or full-length theses.


## Why Choose MyST
Standard Markdown is too limited for a thesis; it lacks native support for the complex structures researchers need. {index}`LaTeX` is often way too complex for writers who don't specialize in IT.

MyST effectively combines the ease of Markdown with the precision and typographic quality of LaTeX. It removes the need to directly manage complex `.tex` files and eliminates many of the common sources of compilation errors associated with traditional LaTeX workflows.

Instead, authors work with clean, lightweight Markdown files, often with live preview capabilities, while MyST handles formatting, numbering, and styling automatically in the background. This results in a faster and more efficient workflow, particularly for large or collaborative documents.

Furthermore, MyST is:

* **Open-source and free to use**
* **Cross-platform**, working consistently across operating systems
* **Version-control friendly**, enabling efficient collaboration through Git [@git]

These advantages make it especially suitable for multi-author academic projects such as theses and dissertations.

## Bridging the Gap with MyST

LaTeX remains the gold standard for scientific publishing, particularly in fields such as engineering, physics, and mathematics, where it is widely used by organizations like IEEE and platforms such as arXiv. However, its complexity can be a barrier for many users, especially ones not studying IT.

MyST addresses this challenge by combining the simplicity of Markdown with the power of LaTeX. Authors can write in a clean, readable syntax while still leveraging advanced features such as mathematical notation, cross-referencing, and structured layouts. It combines the best of both worlds.

```{figure} /content/images/myst_stack.png
:label: mystmd-stack.

The MyST Stack
```

MySTMD uses it's own stack to translate Markdown and Jupiter Notebook Files into many different formats.
The parser reads this source and converts it into an Abstract Syntax Tree (AST). The AST represents the document's structure and meaning rather than its visual appearance. Once the AST has been created, it can be processed by different renderers to produce the desired output format. For example, the same AST can be rendered into HTML for web publication or LaTeX, which can subsequently be compiled into PDF.

As a result, MyST provides an efficient and accessible alternative for creating high-quality academic documents, effectively bridging the gap between ease of use and professional typesetting.


## Comparison with MS Word
The default thesis template used by students at the University of Thessaly is typically based on Microsoft Word.
Microsoft Word offers an easy to digest, WYSIWYG editor that is widely adopted, while MyST/Latex offers an alternative that is often better suited for large, structured, and technical documents. 

The following table summarizes key differences:

| Aspect                              | LaTeX/MyST                                    | Microsoft Word                             |
| ----------------------------------- | --------------------------------------------- | ------------------------------------------ |
| **Mathematics & Technical Content** | Native LaTeX equations and precise formatting | Basic equation editor with limitations     |
| **Performance**                     | Stable, modular, and efficient                | Performance may degrade in large documents |
| **Version Control**                 | Modular and lightweight, perfect with Git     | Binary format, prone to merge conflicts    |
| **Availability**                    | Free, open-source and cross platform          | Requires Microsoft subscription            |
| **Ease of Use**                     | CLI, Steep Learning Curve                     | Beginner-friendly graphical interface      |

Overall, MyST provides a balanced solution that matches the output quality of Word while offering greater flexibility, reproducibility, and scalability through its integration with modern development tools.


## Barrier to entry
Despite all of MyST's successes, there are some things to note before adopting MyST for academic purposes. 

1. MyST is an evolving project that's not as mature as it's competitors. That means that bugs can be expected and troubleshooting is not straight-forward.

2. MyST is a Command Line Interface (CLI) tool, so the user needs to be at least somewhat comfortable with using the terminal, editing config files, and installing the required runtime environments (Node.js and Python).

3. The transition from a WYSIWYG editor like Microsoft Word and LibreOffice can be tough for a new user, as they are required to learn Markdown/MyST specific syntax to reproduce the same result as in those editors.
