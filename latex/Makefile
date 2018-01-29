LATEX=pdflatex

DOC=fft_book

SECTIONS=sine.tex

FIGURES=triangle.pdf triangle_graph.pdf sine_plot.pdf
        

$(DOC).pdf:	$(FIGURES) $(SECTIONS) $(DOC).tex $(DOC).aux $(DOC).ind
	$(LATEX) -halt-on-error $(DOC).tex > /dev/null

$(DOC).idx: $(DOC).aux

$(DOC).ind: $(DOC).idx
	makeindex -q $(DOC)

$(DOC).aux:	$(DOC).tex $(SECTIONS) $(FIGURES)
	$(LATEX) -draftmode -halt-on-error $(DOC).tex > /dev/null

clean:
	rm -f $(DOC).log $(DOC).ilg 

clear:	clean
	rm -f $(DOC).aux $(DOC).pdf $(FIGURES) $(DOC).toc $(DOC).idx

triangle.pdf:	triangle.odp
	unoconv triangle.odp

triangle_graph.pdf:	triangle_graph.odp
	unoconv triangle_graph.odp
	
sine_plot.pdf: sine_plot.ps
	ps2pdf sine_plot.ps
