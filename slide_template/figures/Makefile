SRC=$(wildcard *.tex)
PNG=$(SRC:.tex=.png)
SVG=$(SRC:.tex=.svg)
DVI=$(SRC:.tex=.dvi)

all: png dvi svg

png: $(PNG)
dvi: $(DVI)
svg: $(SVG)


%.png: %.tex
	tikz2png.sh $<


%.dvi: %.tex fig_preamble.latex
	latex -jobname=$* "\input{fig_preamble.latex} \begin{document} \input{$<} \end{document}"

%.svg: %.dvi
	dvisvgm --libgs=$(LIBGS) -n -TS2,2 $<

