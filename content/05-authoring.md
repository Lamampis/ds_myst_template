# Authoring a Document

After installing and configuring the environment, authors can begin writing their documents. This chapter outlines all the necessary information for authoring a document using this template.

After following these steps, you will be able to:

1. Create and edit Markdown files.
2. Include images, bibliographies, and an index.
3. Manage MyST configuration files.
4. Compile everything into a PDF document.

## Recommended Software

While it is possible to use any text editor to author documents with MyST, an {abbr}`IDE (Integrated Development Environment)` is highly recommended for convenience.

An IDE offers features that streamline the workflow, most notably an integrated terminal for running MyST CLI commands.

Popular choices include [Visual Studio Code](https://code.visualstudio.com/) and [Zed](https://zed.dev/).

```{figure} /content/images/IDE.png
:label: fig-zed-ide
:width: 60%

The Zed IDE interface.
```

## Creating Markdown Files

All Markdown source files reside in the `/content` directory. Each `.md` file represents its own chapter or section in the final document, meaning that the number of files directly reflects the entries in the Table of Contents.

The top-level heading (`# Heading 1`) inside each file serves as its TOC title.

While files do not require a specific naming scheme, prefixing them with numbers, such as `01-introduction.md` and `02-analysis.md`, is recommended to maintain the desired order.

For example:

```text
content/
├── 01-introduction.md
├── 02-analysis.md
├── 03-results.md
├── 05-authoring.md
├── index.md
└── images/
    └── IDE.png
```

## Images

Images should be placed inside the `/content/images` folder.

For simple images, standard Markdown syntax can be used:

```markdown
![Alt text](/content/images/image.png)
```

For images that require captions, labels, numbering, or cross-referencing, the MyST `{figure}` directive is recommended:

## Bibliography

In addition to Markdown files, the `/content` folder contains `references.bib`, a plain-text BibTeX database storing bibliographic entries such as books, articles, and websites.

For example:

```bibtex
@book{lamport1994latex,
  author    = {Leslie Lamport},
  title     = {{\LaTeX}: A Document Preparation System},
  edition   = {2nd},
  publisher = {Addison-Wesley},
  address   = {Reading, Massachusetts},
  year      = {1994}
}

@article{knuth1984literate,
  author    = {Donald E. Knuth},
  title     = {Literate Programming},
  journal   = {The Computer Journal},
  volume    = {27},
  number    = {2},
  pages     = {97--111},
  year      = {1984},
  publisher = {Oxford University Press}
}

@online{mystdocs2024,
  author    = {Executable Books},
  title     = {MyST Markdown Documentation},
  url       = {https://mystmd.org},
  urldate   = {2026-10-04},
  year      = {2024}
}
```

Once an entry has been added to `references.bib`, it can be cited anywhere in the document using the citation key:

```markdown
[@lamport1994latex]
```

For example:

```markdown
LaTeX is a document preparation system [@lamport1994latex].
```

MyST will process the citations and generate the bibliography during compilation, provided that the bibliography is configured in `myst.yml`.

## Index

To generate an index of terms and phrases, create an `index.md` file inside the `/content` directory.

The file should contain the following MyST directive:

\{show-index\}

The index file can then be included in the project structure through `myst.yml`:

```yaml
toc:
  - file: content/index.md
  - file: content/01-introduction.md
  - file: content/02-analysis.md
```

## Editing `myst.yml`

The primary configuration file for the project is `myst.yml`.

It defines project metadata, the document structure, and other configuration options used during compilation.

### Personal Information

Customize the thesis metadata by editing the fields under the `options:` section in `myst.yml`:

```yaml
options:
  thesis_title: MyST Markdown Thesis
  university: University of Thessaly
  school: School of Technology
```

These values can then be used by the project's template to populate the appropriate thesis metadata.

### Project Structure

Specify the order of the chapters by listing the Markdown files in the `toc` section of `myst.yml`.

For example:

```yaml
toc:
  - file: content/01-introduction.md
  - file: content/02-analysis.md
  - file: content/03-results.md
  - file: content/05-authoring.md
  - file: content/index.md
```

The order of the entries in `toc` determines the order in which the documents appear in the generated document.

## Compiling the Document

Once the document has been authored and configured, it can be compiled into a PDF using the MyST CLI.

Run the following command from the project root:

```bash
myst build --pdf
```

If the project configuration specifies a PDF output, MyST will generate the PDF according to the configured project settings.

During compilation, MyST may also create a `_build` directory containing generated files and build artifacts. This directory can generally be removed and regenerated when needed.

Before building the complete document, it can be useful to run:

```bash
myst build
```

This allows the Markdown and project configuration to be checked without explicitly requesting PDF output.

After making changes to the source files, run the build command again to regenerate the document.
