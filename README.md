# Tests with R Markdown

## Why

As a LaTeX fan, i like the idea of compiling documents to .pdf format.

R Markdown is a powerful document builder since it can execute code and show the result in a PDF document.

## Usage

The greatest difficulty is using R Markdown outside R Studio (I don't like it. Yet!)

In the end, I created a function in bash, and use it to compile the documents!

In .rmark.sh (filename is arbitrary)
```{bash}
#!/bin/bash

rmd() {
    echo "[INFO 1]    Trying to compile $1.Rmd"

    if [ ! -f "./$1.Rmd" ]
    then
        echo "[INFO 2]    File not Found"
        echo "[INFO 3]    Aborting"
    else
        echo "[INFO 2]    Compiling $1.Rmd"
        R -e "rmarkdown::render('$1.Rmd', 'pdf_document')"
    fi
}
```

## Why you use "hello" for filenames?

For testing!!!