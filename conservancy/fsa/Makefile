SUFFIXES=.dvi .tex .pdf
FILE=buildbot-sponsorship-agreement

all: view

view: $(FILE).dvi
	xdvi $<

clean:
	rm -f $(FILE).{pdf,log,aux,dvi}

.tex.pdf:
	pdflatex $<

.tex.dvi:
	latex $<

