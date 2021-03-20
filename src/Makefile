TARGET := main.pdf

.PHONY: all clean distclean

all: $(TARGET)

clean:
	$(RM) *.aux *.bbl *.blg *.dvi *.log *.toc

distclean: clean
	$(RM) $(TARGET)

%.pdf: %.dvi
	dvipdfmx $<

%.dvi: %.tex title.tex contents references.bib
	uplatex -interaction=batchmode $<
	pbibtex $*
	uplatex -interaction=batchmode $<
	uplatex -interaction=batchmode $<
