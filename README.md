# DS MyST Markdown Thesis Template

## Overview
A simple to use MyST template made for writing scientific papers tailored for UTH's Digital Systems students.

This project aims to replace the existing Microsoft Word template, allowing students to use MyST's and LaTeX's powerful tooling to easily create quality, lightweight documents.

Features:
- MyST directives for equations, citations, figures, cross-references
- Automated references/bibliography with bibtex
- Output to multiple formats: PDF/HTML/DOCX
- Single file configuration
- Digital Signature Support
- Version control with git

IMAGE
![](images/showcase.jpg)

## Prerequisites
- Python 3.8+
- Git
- MyST LINK
- LaTeX utilities (latexmk, xelatex, texlive-core, texlive-latexextra)
- A code editor is optional but recommended.

## Quickstart

Open a terminal window and run the following commands:

`
git clone https://github.com/Lamampis/ds_uth_thesis.git
cd ds_uth_thesis
myst init
`

You can edit the options inside myst.yml to configure the project to your liking. Once you are ready, 
you can create the document by running:

`myst build --pdf`

The standard output file will be named thesis.pdf and placed in the project's root directory.

You are good to go! You can start editing files in the /content folder and add your own images in the /images folder.
You can recomplile after any change by running myst build --pdf.

## Important Tips:
- Bibliography is handled by references.bib inside the /content folder by default.
- Editing the ds_uth_thesis template folder is not recommended nor needed. Only edit if you know what you are doing!
- The _build folder is created temporarily for each build and can be deleted.
- Greek Characters are not yet supported.

## Contributing
This project is very much still ongoing and not ready to be used. However, anybody is welcome to contribute in any way they can. More specifically, I'm looking for ways to make Greek characters work, and a more elegant way to handle the abstract, preferably in a standalone md file and not inside myst.yml.
