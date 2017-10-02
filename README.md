# ucl-lyx-thesis
PhD thesis template in Lyx for UCL students. This template is *NOT* officially
endorsed by UCL. This is merely my Lyx setup when I wrote my PhD thesis. Please
use at your own risk. It is strongly recommended that you check UCL's official
web site for thesis formatting.

## Information

* Each chapter has its own folder, inside containing a folder for images, and a
  chapter Lyx file. The main file `phd_thesis.lyx` includes all the chapters.

* This setup assumes that all chapters share one single `.bib` file which is
  `thesis_bib.bib`.

* The `preamble.tex` file is imported into each chapter Lyx file. Further, each
  chapter Lyx file can be compiled on its own. When compiling a chapter Lyx,
  you will see a table of contents and a bibliography of the chapter. However,
  when the master Lyx (`phd_thesis.lyx`) includes the chapters, these tables of
  contents and chapter specific bibliographies will be removed automatically.
  This automatic inclusion/exclusion is achieved by simply using 
    
        \ifdefined\FULLTHESIS\else (include table of contents) \fi
  
  This basically means "if the variable `\FULLTHESIS` does not exist (meaning
  we are compiling a chapter file on its own), then include a table of
  contents." In the beginning of the master Lyx file, you will see 

        \newcommand{\FULLTHESIS}{}

  This defines the variable `\FULLTHESIS` so that chapter specific tables of
  contents are not included when compiling the master Lyx.

