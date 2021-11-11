# Joshua Ku's Resume

[![Apache license](https://img.shields.io/github/license/Aarif123456/modern-deedy?style=for-the-badge)](http://www.apache.org/licenses/)

This resume template was inspired from [modern-deedy](https://github.com/Aarif123456/modern-deedy)

## Setup

This resume needs to be compiled with `xelatex`. 

### Linux

Run `apt install texlive-xetex latexmk` to install the xelatex package

#### VS Code

1. Install the VS Code Extension [Latex Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
1. In the `settings.json` configure `latex-workshop.latex.tools` to contain the following entry
    ```json
    {
        "name": "xelatex",
        "command": "xetex",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "%DOC%"
        ],
        "env": {}
    }
    ```
1. In the `settings.json` configure `latex-workshop.latex.tools` to replace the default `latexmk` tool with the following entry
   ```json
    {
        "name": "latexmk",
        "command": "latexmk",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "-xelatex",
            "-outdir=%OUTDIR%",
            "%DOC%"
        ],
        "env": {}
    }
    ```
1. In the `settings.json` configure `latex-workshop.latex.recipes` to delete the `"pdflatex ➞ bibtex ➞ pdflatex×2"` recipe and replace it with the following recipe
   ```json
   {
        "name": "xelatex",
        "tools": [
            "xelatex",
        ]
    }
    ```
1. Save the file and restart VS Code to load in your new configuration. After that any changes to a latex file will automatically be created into a pdf

### Windows

Just install [MikTeX](https://miktex.org/download) and install the necessary packages. It comes bundled with a basic GUI editor called TexWorks that does the job well.

## Building

### Linux

In the command line run the following command: `latexmk -xelatex -synctex=1 -interaction=nonstopmode -file-line-error resume.tex`

If you are using VS Code just click `Build LaTex Project` in the LaTex extension window.

The output should be called `resume.pdf`

### Windows

There will be an option to build the project and render the PDF in TexWorks
