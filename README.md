# TU Darmstadt LaTex Thesis Template

This was the template for one of my theses at the [TU Darmstadt](http://www.tu-darmstadt.de/index.en.jsp).

## Table of Content

- [How to use](#how-to-use)
- [Features](#features)
  - [Formulas](#formulas)
  - [Colors for corporate design](#colors-for-corporate-design)
  - [Tables](#tables)
  - [To-do notes](#to-do-notes)
  - [List of Symbols](#list-of-symbols)
  - [List of Acronyms](#list-of-acronyms)
  - [Beautiful graphs](#beatiful-graphs)
    - [Bar charts](#bar-charts)
    - [Pie charts](#pie-charts)

## How to use

1. Download tud-design packages from the [physics department](http://exp1.fkp.physik.tu-darmstadt.de/tuddesign/)

2. Download the fonts for corporate design. You need a student account for the university in order to download the fonts.

3. Install the packages as described in the [manual](http://exp1.fkp.physik.tu-darmstadt.de/tuddesign/)

4. Edit the template from this repo according to your needs

5. Run `latex`

5. Run `makeglossaries thesis` from the command line to sort and typeset glossaries and list of acronyms/symbols

5. Run `latex` for the last time and enjoy the output

## Features

All features can be used in any LaTeX document and don't depend on the tud classes.

### To-do notes

```
\usepackage[ngerman]{todonotes}
```

```
\todo{my first to-do}
```

```
\todo[noline]{my second to-do}
```

```
\todo[inline]{my third to-do}
```

```
\missingfigure{Add an awesome figure here}
```

```
\listoftodos
```

### Colors for corporate design

Define your own colors for later use in graphs or text.

```
\definecolor{blue_1a}{RGB}{93,133,195}
\definecolor{green_3a}{RGB}{80,182,149}
\definecolor{red_8a}{RGB}{238,122,52}
```

### Tables

For tables I used the [ctable](http://texdoc.net/texmf-dist/doc/latex/ctable/ctable.pdf) package. It allows to specify a seperate caption for the toc and therefore enables citations inside the table's caption. It also allows us to write footnotes directly below the table to further explain certain facts.

```
\ctable[
	cap = Wirtschaftslage und Prognose für Österreich,
	caption = Wirtschaftslage und Prognose für Österreich \cite{verbraucher2011, prognose2011},
	label	= tab:inflation,
	pos = htb
	]{lrr}
	{
		\tnote[1]{Veränderung des Verbraucherpreisindex}
		\tnote[2]{Index 1990 = 100}
		\tnote[3]{Prognosewerte}
	}
	{\FL	Jahr			& Inflationsrate in \%\tmark[1]		& Preisentwicklung\tmark[2]
	\ML		2000			& 2,3								& 125,7
	\NN		2001			& 2,7								& 129,1
	\NN		2002			& 1,8								& 131,5
	\NN		2003			& 1,3								& 133,2
	\NN		2004			& 2,1								& 136,0
	\NN		2005			& 2,3								& 139,1
	\NN		2006			& 1,5								& 141,2
	\NN		2007			& 2,2								& 144,3
	\NN		2008			& 3,2								& 148,9
	\NN		2009			& 0,5								& 149,6
	\NN		2010			& 1,9								& 152,4
	\NN 	2011\tmark[3]	& 2,1								& 155,6
	\NN		2012\tmark[3]	& 1,8								& 158,4
	\LL}
```

### Formulas

The big advantage of LaTex is how nicely complex formulas are handled.

Formula for extraterrestrial radiation. Taken from **Renewable and Efficient Electric Power Systems** by Gilbert M. Masters on page 432, 7.43.
```
\begin{equation}
  \glsentrytext{I0} = \frac{24}{\pi} \glsentrytext{SC} \left[1+0,034\cos\left(\frac{360\glsentrytext{n}}{365}\right)\right](\cos \glsentrytext{L} \cos \glsentrytext{delta} \sin \glsentrytext{HSR} + \glsentrytext{HSR} \sin \glsentrytext{L} \sin \glsentrytext{delta})
\end{equation}
```

Seite 95

```
\begin{equation}
	\overline P_w = \frac{c_1}{T} \int_0^T v_w^3\,dt \ne c_1 \left(\frac{1}{T}\int_0^T v_w\,dt\right)^3 = c_1 \cdot \overline{v}_w^3.
\end{equation}
```



### List of acronyms

```
\newacronym{PVGIS}{PVGIS}{Photovoltaic Geographical Information System}
```

### List of symbols

```
\newglossaryentry{IDC}{name=\ensuremath{\bar I_{\textnormal{DC}}}, symbol={kWh/m\ensuremath{^2} pro Tag}, description={Durchschnittliche diffuse Sonneneinstrahlung auf eine Kollektoroberfläche}, type=symbolslist}
```

### Beautiful graphs

#### Bar charts

#### Stacked bar charts

#### Pie charts

### Crisp electronic circuits

```
\begin{tikzpicture}[
	circuit ee IEC,
	set inductor graphic=var inductor IEC graphic,
	scale = 0.85,
	]
	\draw (0,0) to [current source] (0,3);
	\draw (0,3) to [current direction={info=$I_\textnormal{Ph}$}] (2,3);
	\draw (2,3) -- (4,3);
	\draw (2,3) to [current direction={info={$I_\textnormal{D}$}}] (2,1.5) to [diode] (2,0);
	\draw (0,0) to (8,0);
	\draw (4,0) to [resistor={info={$R_\textnormal{P}$}}] (4,3);
	\draw (4,3) to [resistor={info={$R_\textnormal{S}$}}] (6,3);
	\draw (6,3) to [current direction={info={$I_\textnormal{L}$}}] (8,3);
	\draw (8,3) to [resistor={info={$R_\textnormal{L}$}}](8,0);
	\draw [->] (6,2.8) -- (6,0.2);
	\draw (6,1.5) node[anchor=west]{$U_\textnormal{L}$};
\end{tikzpicture}
```

### Custom bibliography

```
\usepackage[style=numeric, firstinits=true]{biblatex}
\urlstyle{same}
\DeclareFieldFormat{title}{#1\isdot}
\renewcommand{\labelnamepunct}{\addcolon\space}
\renewcommand{\multinamedelim}{\addsemicolon\space}
\renewcommand{\finalnamedelim}{\addsemicolon\space}
\DeclareNameFormat{default}{\usebibmacro{name:last-first}{#1}{#4}{#5}{#7}\usebibmacro{name:andothers}}
\DefineBibliographyStrings{ngerman}{urlseen={abgerufen am}}

\bibliography{bibliography}
```

## Acknowledgements

Clemens v. Loewenich and Johannes Werner for creating the tud classes.