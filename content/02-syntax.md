# Markdown and MyST Typography

MyST is a powerful extension of Markdown designed to simplify the creation of high-quality, publishable computational documents. It builds upon the widely used CommonMark specification while incorporating elements from reStructuredText and Pandoc. This combination enables users to write documents that are both human-readable and structurally rich.

MyST supports all standard inline Markdown formatting, allowing authors to emphasize and distinguish text effectively. In addition to extending Markdown’s syntax, MyST integrates with **unist** and **mdast**, which are standardized abstract syntax trees used within the unifiedjs ecosystem. These tools provide robust support for analyzing, transforming, and exporting content, making MyST particularly suitable for technical writing, scientific publishing, and academic workflows.

This chapter will introduce the most common and important pieces of Markdown and MyST syntax the user is likely to need when authoring their documents.

## Text Styling

* **Bold text** is created using double asterisks:
  `**bold**`

* *Italic text* can be written using single asterisks or underscores:
  `*italic*` or `_italic_`

* `Inline code` is wrapped in backticks:
  `` `code` ``

These formatting tools enhance readability and help highlight key concepts or technical terms.

## Headers (H1–H6)

Headers play a crucial role in organizing and structuring a document. They define sections and subsections, improving readability and navigation.

To create a header, prepend a word or phrase with the `#` symbol:

```
# Header Level 1
## Header Level 2
### Header Level 3
```

Up to six levels of headers are supported, with each additional `#` representing a deeper level in the document hierarchy. Proper use of headers ensures a logical structure, which is especially important in long documents such as theses or reports.

MyST will automatically number each header accordingly after document compilation.

## Lists

Lists are essential for presenting information in a structured and concise way.

### Unordered Lists

Unordered lists use dashes (`-`) to represent items:

- Item 1
- Item 2
  - Sub-item
  - Sub-item
- Item 3

```
- Item 1
- Item 2
  - Sub-item
  - Sub-item
- Item 3
```

### Ordered Lists

Ordered lists use numbers to indicate sequence:
1. First item
2. Second item
3. Third item

```
1. First item
2. Second item
3. Third item
```

Lists can also be nested to represent hierarchical relationships between items.

## Quotes

Block quotes are used to highlight important statements or references:

> This is a quote.

```
> This is a quote.
```

They are particularly useful in academic writing when citing definitions or emphasizing key ideas.

## Horizontal Line

A horizontal rule visually separates sections of content:

---

```
---
```

## Images

Images can be embedded using standard Markdown syntax:

![alt text](/content/images/sunset.png "optional title")

```
![alt text](/content/images/sunset.png "optional title")
```

## Links

Links can be defined inline or referenced externally:

[Google Link][key]

[key]: https://www.google.com "Google"

```
[Google Link][key]

[key]: https://www.google.com "Google"
```

## Code Blocks
Code blocks are used to display programming code in a clear and readable format. MyST supports both standard Markdown code blocks and enhanced directive-based blocks.

### Standard Code Block

```python
print("This is Python")
```

\`\`\`python
print("This is Python")
\`\`\`

### MyST Code Block with Options

```{code-block} python
:linenos:
:emphasize-lines: 2,3

import numpy as np

def calculate_energy(mass):
    c = 299792458  # Speed of light (m/s)
    return mass * (c ** 2)
```

\`\`\`{code-block} python
:linenos:
:emphasize-lines: 2,3

import numpy as np

def calculate_energy(mass):
    c = 299792458  # Speed of light (m/s)
    return mass * (c ** 2)
\`\`\`

## Abbreviations: 

To create an abbreviation, you can use the {abbr} role, in HTML this will ensure that the title of the acronym or abbreviation appears in the title when you hover over the element. 

Well {abbr}`MyST (Markedly Structured Text)` is cool!

```
Well {abbr}`MyST (Markedly Structured Text)` is cool! 
```

## Mathematical Expressions

MyST supports LaTeX-style mathematics, both inline and in block form:

* Inline: $a^2 + b^2 = c^2$ (`$a^2 + b^2 = c^2$`)
* Fraction: $\frac{x+1}{y-1}$ (`$\frac{x+1}{y-1}$`)
* Powers and Subscripts: $x_{i}^{2}$ (`$x_{i}^{2}$`)
* Square Root: $\sqrt{x^2 + y^2}$ (`$\sqrt{x^2 + y^2}$`)
* Limits: $\lim_{x \to \infty} \frac{1}{x} = 0$ (`$\lim_{x \to \infty} \frac{1}{x} = 0$`)

This functionality is essential for scientific and engineering documents.

```{math}
:label: math:square_root
\sqrt{x^2 + y^2}
```

## Tables

Tables can be written using the standard Github Flavoured Markdown syntax: https://github.github.com/gfm/#tables-extension-

| foo | bar |
| --- | --- |
| baz | bim |

```
| foo | bar |
| --- | --- |
| baz | bim |
```

They can also be written like this:

```{table} Pinakas
:name: table:test1
| Feature       | Type        | Status    | Notes                  |
| :------------ | :---------: | :-------: | :--------------------- |
| Admonitions   | Directive   | Supported | Useful for call-outs   |
| Equations     | Role        | Supported | Uses LaTeX syntax      |
| References    | Role        | Essential | Enables cross-linking  |
```

```
```{table} Pinakas
:name: table:test1
| Feature       | Type        | Status    | Notes                  |
| :------------ | :---------: | :-------: | :--------------------- |
| Admonitions   | Directive   | Supported | Useful for call-outs   |
| Equations     | Role        | Supported | Uses LaTeX syntax      |
| References    | Role        | Essential | Enables cross-linking  |
```
```

```
```{list-table} Math Constants
:header-rows: 1

* - Name
  - Symbol
  - Approximate Value
* - Pi
  - $ \pi $
  - $ 3.14159 $
* - Euler's Number
  - $ e = \lim_{n \to \infty} (1 + \frac{1}{n})^n $
  - $ 2.71828 $
```
```

```{list-table} Math Constants
:header-rows: 1

* - Name
  - Symbol
  - Approximate Value
* - Pi
  - $ \pi $
  - $ 3.14159 $
* - Euler's Number
  - $ e = \lim_{n \to \infty} (1 + \frac{1}{n})^n $
  - $ 2.71828 $
```

## MyST Syntax Extensions

MyST extends Markdown by introducing **directives** and **roles**, enabling advanced document features.

* **Directives** are block-level elements used for figures, notes, code blocks, and more.
* **Roles** are inline elements used for references, citations, and inline math.

These features make MyST particularly suitable for scientific and technical documentation.

## Figures

Figures can be defined using directives:

```{figure} /content/images/latex_logo.png
:label: latex-logo
:width: 20%

LaTeX Logo
```


```
```{figure} /content/images/latex_logo.png
:label: latex-logo
:width: 20%

LaTeX Logo
```

Figures can then be referenced elsewhere in the document, improving coherence and navigation.

## Admonitions

Admonitions are visually distinct blocks used to highlight important information.

:::{note}
This is a note.
:::

```
:::{note}
This is a note.
:::
```

These elements improve readability and draw attention to critical points.

## Glossary

The Glossary is a collection of definitions for technical terms used in a document.

:::{glossary}
Markdown
: Markdown is a lightweight markup language for creating formatted text using a plain-text editor.
:::

```
:::{glossary}
Markdown
: Markdown is a lightweight markup language for creating formatted text using a plain-text editor.
:::
```

You can use *{term}`Markdown`* to write notes.

Every term will be added automatically to the bottom of the document, in the **Glossary** section, along with the number of the page it's located at.

## Index
Index pages show the location of various terms and phrases that are defined throughout the document. They will show an alphabetized pointer to all Terms and Index entries that are defined.

We can define index entries in two ways:

```
:::{index} Index
:::
```

:::{index} Index
:::

This will show no text, but an index entry will be created in the index that points to the location of the term.

Multiple entries can be created with a single directive:

```
:::{index} Apples, Oranges
:::
```

You can also add an index entry like so:

```
We can solve this problem using {index}`dynamic programming`
```

An index containing all indexed terms and phrases in alphabetical order along with their page number location can be created with:

````
```{show-index}
```
````

## Cross Referencing

```{figure} https://github.com/rowanc1/pics/blob/main/mountains.png?raw=true
:label: mountain-figure
:align: center

This mountain looks awesome
```

````
```{figure} https://github.com/rowanc1/pics/blob/main/mountains.png?raw=true
:label: mountain-figure
:align: center

This mountain looks awesome
```
````

We can point to it later with:
Check out [](#mountain-figure)!!

```
Check out [](#mountain-figure)!!
```
