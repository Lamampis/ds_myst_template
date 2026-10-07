# Environment Setup

The tools required to use this template are not preinstalled on most operating systems. This chapter explains how to install the necessary software and prepare your computer for writing and compiling documents with MyST Markdown.

After completing these steps, you should have {index}`MyST`, Git, LaTeX, and a suitable code editor installed and ready to use.

## Prerequisites

The following software is required:

* **Python 3.8+**
* **Git**
* **MyST Markdown**
* **LaTeX**, including `xelatex` and `latexmk`
* A code editor, such as [Visual Studio Code](https://code.visualstudio.com/) or [Zed](https://zed.dev/)

For detailed MyST installation instructions, see the [official MyST documentation](https://mystmd.org/guide/installing).

## Windows

On Windows, the recommended way to install MyST is through **npm**.

### Install Node.js

Download and install the current LTS version of [Node.js](https://nodejs.org/).

After installation, open PowerShell or Command Prompt and verify that Node.js and npm are available:

```powershell
node --version
npm --version
```

### Install MyST

Install MyST globally using npm:

```powershell
npm install -g mystmd
```

Verify the installation:

```powershell
myst --version
```

### Install Git

If Git is not already installed, download it from [Git](https://git-scm.com/).

Verify the installation with:

```powershell
git --version
```

### Install LaTeX

A LaTeX distribution is required to generate the PDF. **TeX Live** or **MiKTeX** can be used on Windows.

* [TeX Live](https://www.tug.org/texlive/)
* [MiKTeX](https://miktex.org/)

After installation, verify that the required commands are available:

```powershell
xelatex --version
latexmk --version
```

If Windows cannot find these commands, restart the terminal. If the problem persists, make sure the LaTeX installation directory has been added to the system `PATH`.

## Ubuntu/Debian

On Ubuntu or Debian, install Python and pip if they are not already available:

```bash
sudo apt update
sudo apt install python3 python3-pip
```

Install MyST with:

```bash
pip install mystmd
```

Verify the installation:

```bash
myst --version
```

### Install LaTeX

For a complete LaTeX installation:

```bash
sudo apt install texlive-full
```

This requires considerable disk space. A smaller installation can be used if necessary:

```bash
sudo apt install \
  texlive-xetex \
  texlive-latex-extra \
  texlive-fonts-recommended \
  texlive-plain-generic \
  latexmk
```

Verify the installation:

```bash
xelatex --version
latexmk --version
```

### Install Required Fonts

If required by the template, install the additional fonts with:

```bash
sudo apt install ttf-mscorefonts-installer
sudo apt install fonts-crosextra-carlito
```

## Downloading the Template

Once the required software has been installed, download the DS UTH thesis template from GitHub:

[DS UTH Thesis Template](https://github.com/Lamampis/ds_myst_template)

Using Git is recommended:

```bash
git clone https://github.com/Lamampis/ds_myst_template.git
cd ds_myst_template
```

You can also download the repository as a ZIP file directly from GitHub and extract it manually.

## Configuring the Template

Open the downloaded project in your preferred code editor.

The main configuration file is:

```text
myst.yml
```

Edit the appropriate options to configure the project, for example:

```yaml
options:
  thesis_title: MyST Markdown Thesis
  university: University of Thessaly
  school: School of Technology
```

The Markdown files that make up the document are stored in the `content/` directory.

## Building the PDF

Make sure that your terminal is located in the project root, where `myst.yml` is located.

Build the PDF using:

```bash
myst build --pdf
```

The first build may take some time because MyST may need to download additional resources.

After making changes to the Markdown files, run the same command again to regenerate the PDF.

You can also preview the document in a browser during development with:

```bash
myst start
```

## Important Information

:::{note} Important Information

* MyST requires **Node.js** for its CLI.
* A valid **LaTeX installation** is required to generate the PDF.
* All Markdown files should be specified in the `toc` section of `myst.yml` in the desired order.
* Bibliographic references are managed through `references.bib` according to the template configuration.
* The `myst.yml` file contains the main project configuration and should be edited when changing the thesis metadata or structure.
* The `_build` directory is generated automatically and normally does not need to be edited.
* The template's internal files should not be modified unless you know what they are used for.
* Greek characters require appropriate font support in the LaTeX configuration.
