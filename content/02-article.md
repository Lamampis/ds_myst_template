# Chapter 2: Lorem Ipsum

"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."

**"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."**


```{figure} /images/1.png
:label: Tools
:width: 30%
:align: right

Here is another image
```

```{figure} https://github.com/rowanc1/pics/blob/main/sunset.png?raw=true
:label: Beach
Relaxing at the beach
```

## Conclusion

There are many opportunities to improve open-science communication, to make it more interactive, accessible, more reproducible, and both produce and use structured data throughout the research-writing process. The `mystjs` ecosystem of tools is designed with structured data at its core. We would love if you gave it a try -- learn to get started at <https://myst.tools>.

We can include simple math using $E=mc^2$.

## Goals and Progress

To create this template, I started of using the prexisting template plain_latex_book by Rowan Cockett
``` https://github.com/myst-templates/plain_latex_book ```
and editing it to match the prexisting DS UTH thesis template made in Word format.

:::{note} Important Note
Everything written here is subject to change as the project advances. It's mostly placed here as a placeholder.
:::


One of the biggest hurdles I faced, is MyST's incompatibility with Greek characters. Apparently, the default behavior
is to escape every Greek character into a match equation symbol when being converted from markdown to tex.
As of yet, I have not been able to work around this issue, and according to MyST's Developers it's an issue they
are looking to fix so I am hopeful that I will be able to write in Greek in the near future.


The goal of this project is to provide UTH's students who wish to write their thesis, an alternative way to do it.
The aim is to be as simple as possible for students to grasp and use. 
MyST provides an elegant way to combine LaTeX's solid tools with easy to use markdown files. MyST has many advantages
over Microsoft Word, such as high quality scientific typesetting, ease of collaboration and fine tuned configuration.


### Some of the standout features of MyST include:
- Native Support for Scientific Typesetting (LaTeX Math)
- Robust Crossreferencing
- Non centralized collaboration
