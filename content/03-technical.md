# Template Architecture
To create a document with MyST, the user needs to have a good understanding of the required files and folder structure. The exact folder structure is not set in stone. This template uses a very standard structure which should fit most needs.

This is how this project is structured like:

```{code-block} python
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

## File Structure

### myst.yml

This is an important file that the user needs to edit in order to personalize their document. It includes options such as **thesis_title**, **university**, ***student_name**, **student_id**, and other important information which the user can fill in.

The other important section is the ToC (Table of Contents) section in myst.yml. As myst does not automatically detect markdown files and their order, the user has to input them manually. MyST will display them in order.

```python
toc:
    - file: content/01-introduction.md
    - file: content/02-behind_myst.md
    - file: content/03-setup.md
    - file: content/04-examples.md
    - file: content/05-technical.md
    
```

## Content Folder

The **/content folder** is where the user will spend most of their time in. This is where the user can create and edit markdown files and add images. This is also where the references.bib file lives.

For example, we can create a file named introduction.md which contains some simple markdown. After we include it in myst.yml as shown earlier, it will be used my MyST when building the document.

## Template Folder

This folder does not have to be edited by the end user and can be ignored. It contains files that create the look and feel of the finished document. However, it is important to document it's inner workings.

The most important file here is template.tex, which acts as the architectural blueprint for the PDF output. While MyST handles the content, the .tex template dictates the visual style, layout, and LaTeX packages used to render that content. Let's go over some important lines:

### Geometry:
The general geometry of the document is defined by the first 2 lines of the template.tex file.
```
\documentclass[a4paper,11pt,oneside]{article}
\usepackage[top=2.7cm, bottom=3.5cm, left=3cm, right=3cm]{geometry}
```

The A4 Paper dimension specification is used in the first line, and in the seond line, margin is applied.

### Packages:
LaTeX does not do much by itself. We include packages with the \usepackage command to style and modify the document.
```
\usepackage{graphicx}
\usepackage{caption}
\usepackage{chngcntr}
\usepackage[numbers,sort&compress]{natbib}
\usepackage{xcolor}
\usepackage{changepage}
\usepackage{framed}
\usepackage{hyperref}
\usepackage{amssymb}
\usepackage{amsmath}
\usepackage{fancyhdr}
\usepackage{setspace}
\usepackage{titlesec}
\usepackage{fontspec}
\usepackage{polyglossia}
```

Each one of these included packages provide a different function that adds something to the template.

### Styling:
Much of what makes a document readable and workable is styling. That includes fonts, header sizes, page and figure numbering and line spacing.

Here we define the font, the document's main and secondary language, line spacing, and page numbering style:
```
\setmainfont{Carlito}
\newfontfamily\greekfont{Carlito}
\setmainlanguage{english}
\setotherlanguage{greek}
\setstretch{1.5}
\pagenumbering{arabic}
```

This is how to change the header sizes for #, ##, and ### headers
```
\titleformat{\section}
{\normalfont\fontsize{20pt}{24pt}\bfseries}{\thesection}{1em}{}

% ##
\titleformat{\subsection}
{\normalfont\fontsize{16pt}{20pt}\bfseries}{\thesubsection}{1em}{}

% ###
\titleformat{\subsubsection}
{\normalfont\fontsize{12pt}{16pt}\bfseries}{\thesubsubsection}{1em}{}
```

These lines are used to show the page number on the right.
```
\pagestyle{fancy}
\fancyhf{}
\fancyfoot[R]{\thepage}
\renewcommand{\headrulewidth}{0pt}


\fancypagestyle{plain}{%
  \fancyhf{}
  \fancyfoot[R]{\thepage}
  \renewcommand{\headrulewidth}{0pt}
}
```

## Template Variables
MyST can dynamically inject data defined in other files in template.tex. The syntax for that is [- -]
For example, we can inject the student's name by typing ```[- doc.options.student_name -]``` in template.tex, and adding a student_name field in the options section inside myst.yml like so:
```
  options:
    student_name: Charalampos Anastasiou
```
Inside myst.yml

MyST also knows when to start displaying the markdown files by looking for the ```[- CONTENT -]``` line.


## Pages Before Mainmatter:
Part of the template is recreating the original document structure like it was with the current Microsoft Word template. These pages were recreated in LaTeX and are part of the template. These include:

- Title page
- Declaration of Ethics
- Examination Comittee
- Abstract
- Acknowledgements
- Table of Contents

This is how the first page is handled. We use the previously mentioned data injections to fill out the user's personal information and use LaTeX styling to make it match the original.

```
\clearpage
\begin{titlepage}
\thispagestyle{empty}
\begin{center}

\includegraphics[height = 0.18\textheight]{../../../ds_uth_thesis/images/uth.png}\\[2cm]

% University
{\fontsize{24pt}{28pt}\selectfont \textbf{[- doc.options.university -]}}\\[0.8cm]

% School
{\fontsize{16pt}{18pt}\selectfont [- doc.options.school -]}\\[0.6cm]

% Department
{\fontsize{16pt}{18pt}\selectfont [- doc.options.department -]}\\[3.0cm]

% Thesis Title
{\fontsize{26pt}{28pt}\selectfont \textbf{[- doc.options.thesis_title -]}}\\[3.5cm]

% Student
{\fontsize{18pt}{20pt}\selectfont [- doc.options.student_name -] ([- doc.options.student_id -])}\\[3.0cm]

% Supervisor
{\fontsize{14pt}{16pt}\selectfont Supervisor: [- doc.options.supervisor -]}\\[1.0cm]

% City + Date
{\fontsize{14pt}{16pt}\selectfont [- doc.options.city -], [- doc.options.thesis_date -]}\\[0.6cm]

\end{center}
\end{titlepage}
\clearpage
```
