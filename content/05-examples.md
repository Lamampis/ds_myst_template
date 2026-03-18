# Features and Examples

Here are some features that I can use for this in the future.

## 1. Lists

Here is an example of as list made in markdown

* First item
* This text is **bold** and this is *italic*.

1.  This is a numbered list.
2.  The numbering automatically adjusts.

### Horizontial Line
---

## 2. Tables

Tables are created using standard Markdown pipe syntax (`|`).

| Feature | Type | Status | Notes |
| :--- | :---: | :---: | :--- |
| Admonitions | Directive | Supported | Good for call-outs. |
| Equations | Role/Directive | Supported | Uses LaTeX syntax. |
| References | Role | Essential | Links to figures, sections, etc. |

### Equations

You can include inline math like $E=mc^2$ or display block equations with numbering.

### Admonitions (Call-Out Boxes)

:::{note} Important Note
MyST Directives (the `:::` blocks) are parsed differently than standard Markdown and provide structural features.
:::

### Code Blocks

```{code-block} python
:linenos:
# This is a Python code example
import numpy as np

def calculate_energy(mass):
    c = 299792458  # Speed of light
    return mass * (c ** 2)
