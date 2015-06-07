pfc-fic-udc
===========

Plantilla latex para el Proyecto Fin de Carrera de la Facultad de
Informática de la Universidad de A Coruña.

Standard LaTeX template for final degree report/book project in FIC, 
(Facultad de Informática) at UDC (Universidad de A Coruña)

# Package Dependencies (Ubuntu 14.04)

* texlive
* texlive-latex-extra
* texlive-extra-utils
* texlive-latex-recommended
* texlive-bibtex-extra
* texlive-science
* texlive-pictures
* texlive-lang-spanish
* latexmk
* aspell
* aspell-es
* make

_latexmk_ is not the same package as _latex-mk_. This one is a perl script
useful to use it in a standard _Makefile_. _aspell_ is an optional package
for spelling checks.


# Source tex structure (`src`):

The main document where the most important variables or macros are defined 
is _pfc.tex_. The style, dependencies and other macros are defined in _pfc.sty_, 
but you won't need to change it.

Tex files with prefix _pfc_*_ are defining  the root structure of the document, 
that is, the mandatory parts of the book: cover, thanks, table of contents, 
glossary, bibliography, etc.

The rest of the tex files are the chapters of the report.

If you want to define glosary or acronym entries, you have to edit the file 
`pfc.glossary`, the same applies for the bibliography using the file `pfc.bib`.

The default folder to include all the pictures is `images`.


# Use

Just edit the macros to define title, author, ... in the file `pfc.tex`.
You can also add or remove includes for each chapter.

## Compile and generate PDF

If you have installed _latexmk_ and _make_ just type `make`:
```
jriguera@packard:~/devel/personal/pfc-udc/src$ make
latexmk -pdf -pdflatex="pdflatex" -use-make pfc.tex
Latexmk: This is Latexmk, John Collins, 11 Nov. 2012, version: 4.35.
**** Report bugs etc to John Collins <collins at phys.psu.edu>. ****
Latexmk: applying rule 'pdflatex'...
Rule 'pdflatex': Rules & subrules not known to be previously run:
   pdflatex
Rule 'pdflatex': The following rules & subrules became out-of-date:
      'pdflatex'
------------

...

Output written on pfc.pdf (41 pages, 294604 bytes).
Transcript written on pfc.log.
Latexmk: Found input bbl file 'pfc.bbl'
Latexmk: Log file says output to 'pfc.pdf'
Latexmk: Found bibliography file(s) [pfc.bib]
Latexmk: All targets (pfc.pdf) are up-to-date
```

You can have a look to the example pdf file `pfc.pdf`.


## Spelling

Type `make spell` to check all tex files.

## Cleaning

To clean  up  (remove) all regeneratable files generated by latex and bibtex: `make clean`
To clean up all generated files (except the _*.tex_, _*.sty_ and _Makefile_: `make dist-clean`

# Author

José Riguera López

