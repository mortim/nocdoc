# Example of fake nocdoc documentation

This is one way to design the whole documentation project.

### Structure

- '**config.noc**' : The entire Noc configuration from specific section.
- subfolder '**content**' : This directory contains all HTML content from specific part.

> You can check this Bash script, [here](https://github.com/noc-lang/manual/blob/main/setup.sh) to:
>   - Convert some Markdown snippets to HTML snippets (not supported in Noc)
>       - It's important to use the same name conventions:
>           - The starting point folder of all HTML wiki content filepaths in all 'config.noc' has 'include_html' name.
>           - The 'home.md' for homepages.
>   - Separate all HTML output files in different directories:
>       - 'manual' directory is generated with this script for the Noc Manual and it looks like [this](https://github.com/noc-lang/manual/tree/gh-pages) inside this directory:
>           - The Noc Wiki at the root
>           - The Noc Library, Nocdoc are generated in a specific directory.

### Building

```
git clone https://github.com/noc-lang/nocdoc
mkdir doc && mv nocdoc doc && cd doc

# or ./setup.sh
noc nocdoc/example/generate_doc.noc [wiki | library]
```