# nocdoc

A basic documentation generator for the [Noc language programming language](https://github.com/noc-lang/noc) written in Noc.

- Check how to build locally the official Noc documentation, [here](https://github.com/noc-lang/docs).

or if you want to document your own Noc functions:

```scala
load nocdoc/nocdoc.noc

def randomFunction1 = {
    ---
    docstring...
    ---
    /* some code... */
}

/* The documented functions can be linked with this id in HTML '[name_function]' (ex: "#[randomFunction1]") */
def moduleFunctions = {
    [
        [randomFunction1]
        /*
        ...
        [randomFunctionN]
        */
    ]
}

def wikiPage1 = {
    "
    HTML content...
    "
}

/* Doc generation */

/* library info */
/* IMPORTANT: You have to keep the same order */
def libInfo = {
    [
        "library_name"
        "author"
        "library_description in HTML..."
        "git repos url"
        /* Table of contents */
        [
            [ "overview"
              [ "index.html"
                "wiki_name.html" ]]

            [ "modules"
              [ "random_module.html" ]]
        ]
    ]
}

/* wiki info */
def wikiInfo = {
    [
        "wiki_name"
        "author"
        "wiki_description in HTML..."
        "git repos url"
        /* Table of contents */
        [
            [ "overview"
              [ "index.html"
                "wiki_name.html" ]]
        
            [ "wiki"
              [ "wiki_page_name.html" ]]
        ]
    ]
}

def main = {
    /* (library_info|wiki_info) generateHomePage */
    /* library_info documented_functions module_name generateModule */
    /* wiki_info html_content wiki_page_name generateWikiPage */
    
    /* example */
    /* A HTML file is generated by these functions */
    libInfo generateHomePage
    wikiInfo generateHomePage
    libInfo moduleFunctions "random_module" generateModule
    wikiInfo wikiPage1 "wiki_page_name" generateWikiPage
}
```
