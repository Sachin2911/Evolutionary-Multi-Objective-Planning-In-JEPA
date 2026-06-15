file=proposal
outdir=..
outname=ResearchProposal_2699183

all:
	pdflatex -interaction=nonstopmode $(file).tex || true
	bibtex $(file)
	pdflatex -interaction=nonstopmode $(file).tex || true
	pdflatex -interaction=nonstopmode $(file).tex || true
	mv $(file).pdf $(outdir)/$(outname).pdf

clean:
	rm -rf $(file).{aux,bbl,blg,lof,log,lot,out,synctex.gz,toc,fdb_latexmk,fls}
