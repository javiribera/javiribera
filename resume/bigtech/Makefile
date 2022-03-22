DVIPS = dvips -t letter -Ppdf
ACROREAD = acroread -geometry 1600x800
GV = ghostview -scale 3
IN = javier_ribera_resume
paper:
	latex $(IN) 
	latex $(IN)
	$(DVIPS) $(IN).dvi > $(IN).ps
	#$(GV) $(IN).ps &
	#ps2pdf -dEmbedAllFonts=true -dSubsetFonts=true -dEPSCrop=true $(IN).ps
	ps2pdf14 -dPDFSETTINGS=/prepress -dEmbedAllFonts=true $(IN).ps
	#$(ACROREAD) $(IN).pdf >& /dev/null &

clean:
	/bin/rm -f $(IN).ps $(IN)*bak
	/bin/rm -f *.aux *.log *.blg *.dvi *.toc *.bbl

embed:
	gs -sDEVICE=pdfwrite -dBATCH -dSAFER -dNOPAUSE -dPDFX -dPDFSETTINGS=/prepress -sOutputFile=javier_ribera_resume.pdf -c'> setdistillerparams' -f javier_ribera_resume.pdf -c quit

