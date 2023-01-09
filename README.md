# nocdoc

A basic documentation generator for the [Noc language programming language](https://github.com/mortim/noc) written in Noc.

To build the Noc documentation, check this [link](https://github.com/mortim/noc/wiki/Installation#building-the-noc-documentation-only-the-v0100).

or if you want to document your own Noc functions:

```scala
load nocdoc.noc

def randomFunction = {
    ---
    docstring...
    ---
    some code...
}

/* Doc generation */

/* documented functions */
def functions = {
    [
        [randomFunction]
    ]
}

/* library info */
/* You have to the keep the same order */
def info = {
    [
        "library_name"
        "author"
        "library_description"
        "git repos url"
        /* Table of contents */
        ["page1.html" ... "pageN.html"]
    ]
}

def main = {
    /* A HTML file is generated */
    /* library_info (optional: documented_functions) (optional: html_filename) is_the_homepage generate */
    /* example */
    info True generate
    info functions "random_module" False generate
}
```
