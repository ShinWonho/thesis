# Makefile for LaTeX projects

# Main LaTeX file name without extension
MAIN = main

# LaTeX compiler (e.g., pdflatex, xelatex)
LATEX = pdflatex

# BibTeX compiler
BIBTEX = bibtex

# Default target
all: $(MAIN).pdf

# Rule to compile the main document
$(MAIN).pdf: $(MAIN).tex # $(MAIN).bbl
	$(LATEX) $(MAIN)
	$(LATEX) $(MAIN)

# Rule to compile the bibliography
$(MAIN).bbl: $(MAIN).tex # reference.bib
	$(LATEX) $(MAIN)
	$(BIBTEX) $(MAIN)
	$(LATEX) $(MAIN)

# Clean auxiliary files
clean:
	rm -f *.aux $(MAIN).bbl $(MAIN).blg $(MAIN).log $(MAIN).out $(MAIN).toc $(MAIN).lof $(MAIN).lot

# Clean all files including the PDF
distclean: clean
	rm -f $(MAIN).pdf

.PHONY: all clean distclean
