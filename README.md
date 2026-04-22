# phd-thesis-template
A LaTeX template for PhD theses in the Data Linguistica series.


## Compiler
LuaLaTeX

### Autocompiling in VSCod*
1. install the LaTeX workshop extension
2. while on the extension page, click on __Manage__ (the cog wheel symbol) > __Settings__
3. in the top toolbar, click __Open Settings (JSON)__ (the incomprehensible document-with-an-arrow symbol)
4. make sure that:
  - `latex-workshop.latex.recipes` contains
    ```json
    {
        "name": "latexmk (lualatex)",
        "tools": [
            "lualatexmk"
        ]
    }
    ```
  - `latex-workshop.latex.tools` contains
    ```json
    {
        "name": "lualatexmk",
        "command": "latexmk",
        "args": [
                "-shell-escape",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-lualatex",
                "-outdir=%OUTDIR%",
                "%DOC%"
                ],
        "env": {}
    }
    ```
  - `latex-workshop.latex.recipe.default` is set to `"latexmk (lualatex)"`
Now you should be able to compile on save.
