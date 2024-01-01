```latex
\usepackage{import}
\usepackage{xifthen}
\usepackage{pdfpages}
\usepackage{transparent}
\newcommand{\incfig}[1]{%
	\def\svgwidth{\textwidth}
	\import{/inkscape figures/}{#1.pdf_tex}
}
```

```latex
	\begin{figure}[ht]
		\centering
		\incfig{t3}
		\caption{三角形}
	\end{figure}
```
