# Chapter 1: Tutorial

To get started with using this template to create PDF files, the user needs to follow these next steps:

---

## For Windows
idk
The TeX system is widely used [@knuth1984texbook].

As noted by Einstein [@einstein1905photoelectric], light behaves
The TeX system is widely used [@knuth1984texbook].

The MystMD docs [@mystdocs] helped me a lot!

## For Linux OS's

### Install Dependancies

Install MyST with one of the officially supported methods: https://mystmd.org/guide/installing

### Install LaTeX from your distribution's package manager:
- Gentoo: sudo emerge xetex latex-extras texlive-core latexmk
- Ubuntu/Debian: sudo apt-install xetex latex-extras texlive-core latexmk
- Arch: sudo pacman -S xetex texlive-core latex-extras latexmk
- Fedora: sudo dnf install xetex texlive-core latex-extras latexmk

---

### How to use the template
1. Download the dsuth myst template

2. Open the folder, preferably in a code editor of your choice

3. Create a .md file in the segments folder (for example chapter1.md)

4. Include your markdown files in the article's section in myst.yml

5. Fill out your information in the file myst.yml

6. Compile the PDF file by running myst build --pdf

By default, the PDF file will be named thesis.pdf and will be in the project's root folder.

Users can use LaTeX syntax to use it's powerful features.

```{figure} /images/1.png
:label: Tools 1
:width: 30%

Here is an image
```
