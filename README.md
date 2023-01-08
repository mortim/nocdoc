# nocdoc

A basic documentation generator for the [Noc language programming language](https://github.com/mortim/noc) written in Noc.

To build the Noc documentation, check this [link](#).

or if you want to document your own Noc functions:

```scala
load nocdoc.noc

def functions = {
    [
        [randomFunction]
    ]
}

def randomFunction = {
    ---
    docstring...
    ---
    some code...
}

def main = {
    /* A HTML file is generated */
    functions "your_lib_name" generateDoc
}
```