# Template Architecture
To create a document with {index}`MyST`, the user needs to have a good understanding of the required files and folder structure. The exact folder structure is not set in stone. This template uses a very standard structure which should fit most needs.

This is how this project is structured like:

```{code-block} python
:name: project_structure
:caption: The project's folder structure

root/
├── content/
│   ├── 01-introduction.md
|   ├── images/
│       └── myst.png
│   └── references.bib
│
├── ds_uth_thesis/
│   └── images/
│       └── uth.png
│   ├── template.tex
│   └── template.yml
└── myst.yml

```

This chapter will explain the utility of each file shown and what the user needs to know before editing these files.

## `myst.yml`

The `myst.yml` file is the main configuration file of the MyST project. It defines the project metadata, bibliography, PDF export configuration, thesis-specific variables, and the order in which the Markdown files are included. The PDF export is configured as follows:

```yaml
exports:
  - output: thesis.pdf
    format: pdf
    template: ./ds_uth_thesis
```

The `options` section contains the variables used by the {index}`LaTeX` template to populate the thesis with student- and thesis-specific information. The main variables are `student_name`, `student_id`, `thesis_title`, `city`, `thesis_date`, and `approval_date`. Information about the examination committee is provided through `supervisor_name`, `supervisor_rank`, `supervisor_dept`, `member1_name`, `member1_title`, `member2_name`, and `member2_title`. The optional `signature_path` specifies the location of the student's signature. Finally, `thesis_abstract_greek` and `thesis_abstract_english` contain the Greek and English abstracts respectively.

The document structure is defined by the `toc` section. The Markdown files are processed in the order in which they appear:

```yaml
toc:
  - file: content/index.md
  - file: content/01-introduction.md
  - file: content/02-syntax.md
  - file: content/03-technical.md
  - file: content/04-setup.md
  - file: content/05-authoring.md
  - file: content/06-conclusion.md
```

Each file represents a separate segment of the document and, in this template, corresponds to a chapter or major section. Changing the order of these entries changes the order in which the chapters appear in the generated document.

## `template.tex`

The `template.tex` file is the LaTeX template responsible for defining the appearance and structure of the generated PDF. It specifies the document type and page layout using:

```latex
\documentclass[a4paper,11pt,oneside]{article}
\usepackage[top=2.7cm, bottom=3.5cm, left=3cm, right=3cm]{geometry}
```

The template uses `fontspec` and `polyglossia` to support both English and Greek text and defines the main font as Carlito:

```latex
\usepackage{fontspec}
\usepackage{polyglossia}

\setmainlanguage{english}
\setotherlanguage{greek}
\setmainfont{Carlito}
\newfontfamily\greekfont{Carlito}
```

Figure and table numbering is configured to include the section number, resulting in numbering such as Figure 2-1 and Table 2-1:

```latex
\counterwithin{figure}{section}
\counterwithin{table}{section}
\renewcommand{\thefigure}{\thesection-\arabic{figure}}
\renewcommand{\thetable}{\thesection-\arabic{table}}
```

The appearance of section headings is customized using `titlesec`:

```latex
\titleformat{\section}
{\normalfont\fontsize{20pt}{24pt}\bfseries}{\thesection}{1em}{}

\titleformat{\subsection}
{\normalfont\fontsize{16pt}{20pt}\bfseries}{\thesubsection}{1em}{}
```

Page numbering is placed at the bottom-right of each page using `fancyhdr`:

```latex
\pagestyle{fancy}
\fancyhf{}
\fancyfoot[R]{\thepage}
\renewcommand{\headrulewidth}{0pt}
```

The most important part of the template is the interaction with MyST. Template expressions such as:

```latex
[- doc.options.thesis_title -]
[- doc.options.student_name -]
[- doc.options.supervisor_name -]
```

retrieve the corresponding values from `myst.yml`. Conditional expressions can also be used for optional content, such as the student's signature:

```latex
[# if doc.options.signature_path #]
  \includegraphics{[- doc.options.signature_path -]}
[# else #]
  \vspace{1.2cm}
[# endif #]
```

Finally, the `[- CONTENT -]` placeholder determines where the content generated from the Markdown files is inserted into the LaTeX document:

```latex
\tableofcontents

[- CONTENT -]
```

Therefore, `myst.yml` provides the **configuration, metadata, and document structure**, while `template.tex` defines the **layout, formatting, and presentation** of the final thesis. This separation allows the same template to be reused while changing only the thesis-specific information and Markdown content.
