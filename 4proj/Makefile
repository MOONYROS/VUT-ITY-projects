#author: Ondrej Lukasek (xlukas15)

ITY_PROJEKT=proj4
INCLUDE=czechiso.bst

$(ITY_PROJEKT).pdf: $(ITY_PROJEKT).ps
	ps2pdf -sPAPERSIZE=a4 $(ITY_PROJEKT).ps

$(ITY_PROJEKT).ps: $(ITY_PROJEKT).dvi
	dvips -t a4 $(ITY_PROJEKT).dvi

$(ITY_PROJEKT).dvi: $(ITY_PROJEKT).tex
	latex $(ITY_PROJEKT).tex
	make bibtex
	latex $(ITY_PROJEKT).tex
	latex $(ITY_PROJEKT).tex
	pdflatex $(ITY_PROJEKT).tex
	make bibtex
	pdflatex $(ITY_PROJEKT).tex
	pdflatex $(ITY_PROJEKT).tex

bibtex: $(ITY_PROJEKT).bib
	bibtex $(ITY_PROJEKT)

clean:
	rm -f $(ITY_PROJEKT).aux
	rm -f $(ITY_PROJEKT).out
	rm -f $(ITY_PROJEKT).dvi
	rm -f $(ITY_PROJEKT).log
	rm -f $(ITY_PROJEKT).ps
	rm -f $(ITY_PROJEKT).synctex.gz
	rm -f $(ITY_PROJEKT).fls
	rm -f $(ITY_PROJEKT).fdb_latexmk
	rm -f $(ITY_PROJEKT).bbl
	rm -f $(ITY_PROJEKT).blg
