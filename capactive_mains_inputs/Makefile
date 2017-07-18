# Makefile to test and plot sections of the curve 
# to test the interpolation table
#
#
#
SOURCE = capacitive_mains_inputs2
TEX_SOURCE = $(SOURCE).tex
PDF_SOURCE = $(SOURCE).pdf

#
#
# Place all .png files here as .dia targets
#
# png files mangle text now in dia
DIA = opto.dia
DIAJPG = opto.jpg

doc: $(DIAJPG)
	echo $?
	gnuplot reactance.gpt 
	pdflatex $(TEX_SOURCE)
	pdflatex $(TEX_SOURCE)
	acroread $(PDF_SOURCE) || evince $(PDF_SOURCE)

bib:	
	bibtex $(SOURCE)

#%.png:%.dia
#	echo $?
#	dia -t png $<
#	mkdir -p images_sw_doc
#	echo $< $@
#	mv $@ images_sw_doc
#	echo $@

%.jpg:%.dia
	echo $?
	dia -t jpg $<
	mkdir -p images_sw_doc
	echo "dia to jpg arg list and target" $< $@
	mv $@ images_sw_doc
	echo $@


#images.tex:
#	cat begin_images.tex > images.tex
#	ls images_sw_doc >> images.tex
#	cat end_images.tex >> images.tex
#

clean:
	rm *.pdf
