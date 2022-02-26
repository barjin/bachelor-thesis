export TEXINPUTS=../tex//:

all: thesis.pdf abstract.pdf

# LaTeX must be run multiple times to get references right
thesis.pdf: thesis.tex $(wildcard *.tex) bibliography.bib thesis.xmpdata
	pdflatex $<
	bibtex thesis
	pdflatex $<
	pdflatex $<

abstract.pdf: abstract.tex abstract.xmpdata
	pdflatex $<

clean:
	find . -type f -regex '.*\.\(log\|dvi\|aux\|toc\|lof\|lot\|out\|bbl\|blg\|xmpi\)' -delete
	rm -f thesis.pdf abstract.pdf
