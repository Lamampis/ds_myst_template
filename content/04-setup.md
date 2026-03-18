# Tutorial / Setup

To get started with this MyST template, you need to ensure you have the following installed on your computer.

## Prerequisites:
- Python 3.8+
- Git
- [MyST](https://mystmd.org/guide/installing) 
- LaTeX utilities (latexmk, xelatex, texlive-core, texlive-latexextra)
- A code editor is optional but recommended.

## Ubuntu/Debian

I recommend installing MyST through pipx:
```
sudo apt install pipx
pipx ensurepath
# Restart your terminal after this
pipx install mystmd
```

Install LaTeX utilities:
```
sudo apt install texlive-full
```

Or if you need are short on storage space:
```
sudo apt install texlive-latex-extra texlive-fonts-recommended, latexmk, texlive-core, texlive-xetex texlive-plain-generic
```

Install Fonts:
```
sudo apt install ttf-mscorefonts-installer
```

## Quickstart

Open a terminal window and run the following commands:

```
git clone https://github.com/Lamampis/ds_myst_template.git
cd ds_uth_thesis
```

You can edit the options inside myst.yml to configure the project to your liking. Once you are ready, 
you can create the document by running:

`myst build --pdf`
(Say yes if you are prompted to install NodeJS)

**You are good to go!** The created file is called thesis.pdf by default. You can start editing files in the /content folder and add your own images in the /images folder.
You can recomplile after any change by running `myst build --pdf`.

## Important Information:
:::{note} Tips:
- Bibliography/References is handled by references.bib inside the /content folder by default.
- All markdown files must be specified in the `toc` section of myst.yml in order.
- Editing the ds_uth_thesis template folder is not recommended nor needed. Only edit if you know what you are doing!
- You must have a valid LaTeX installation to compile the document.
- The _build folder is created temporarily for each build and can be deleted afterwards.
- Greek Characters are not yet supported.
:::
