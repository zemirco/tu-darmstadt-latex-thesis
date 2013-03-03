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
- [Beautiful graphs](#beautiful-graphs)
    - [Bar charts](#bar-charts)
    - [Pie charts](#pie-charts)
    - [Line graph](#line-graph)
    - [Two y-Axes](#two-y-axes)
- [Electronic circuits](#electronic circuits)
- [Text font in images](#text-font-in-images)
- [Custom bibliography](#custom-bibliography)

## How to use

1. Download tud-design packages from the [physics department](http://exp1.fkp.physik.tu-darmstadt.de/tuddesign/)

2. Download the fonts for corporate design. You need a student account for the university in order to download the fonts. This step is optional. Template will also work without the fonts

3. Install the packages as described in the [manual](http://exp1.fkp.physik.tu-darmstadt.de/tuddesign/)

4. Edit the template from this repo according to your needs

5. Run `latex`

6. Run `makeglossaries thesis` from the command line to sort and typeset glossaries and list of acronyms/symbols

7. Run `latex` for the last time and enjoy the output

## Features

All features can be used in any LaTeX document and don't depend on the tud classes.

## To-do notes

Very useful while writing the thesis. Don't forget to delete them before printing the final copy. Enable to-do notes with the **todonotes** package. I usually use the inline style.

```
\usepackage[ngerman]{todonotes}
\todo[inline]{This is a sample to-do note}
```

![To-do notes](https://s3.amazonaws.com/zeMirco/github/latex-template/to-do-notes.png)

Print a list with your open to-do notes using the following command.

```
\listoftodos
```

![To-do list](https://s3.amazonaws.com/zeMirco/github/latex-template/to-do-list.png)

## Colors for corporate design

Define your own colors for later use in graphs or text.

```
\definecolor{blue_1a}{RGB}{93,133,195}
\definecolor{green_3a}{RGB}{80,182,149}
\definecolor{red_8a}{RGB}{238,122,52}
```

## Tables

For tables I used the [ctable](http://texdoc.net/texmf-dist/doc/latex/ctable/ctable.pdf) package. It allows to specify a seperate caption for the toc and therefore enables citations inside the table's caption. It also allows us to write footnotes directly below the table to further explain certain facts.

```
\ctable[
	caption = Technical data of the Mitsubishi i-MiEV \cite{imiev_daten},
	cap = Technical Data of the Mitsubishi i-MiEV,
	label	= tab:data_imiev,
	pos = htb
	]{llr}
	{\tnote[1]{Data measured in NEDC}}
	{\FL Description & Specification & Value
		\ML \multirow{4}*{Dimensions} & Length & 3475 mm
		\NN & Width & 1475 mm
		\NN & Height & 1610 mm
		\NN & Wheel base & 2550 mm
		\ML \multirow{5}*{Load capacity} & Luggage space & 227 / 860 liters
		\NN & Curb weight & 1110 kg
		\NN & Permissible maximum weight & 1450 kg
		\NN & Payload & 340 kg
		\NN & Seats & 4 People
		\ML \multirow{3}*{Driving characteristics} & Energy consumption & 135 Wh/km
		\NN & Range & 150 km\tmark[1]
		\NN & max. Velocity & 130 km/h
		\ML \multirow{5}*{Battery data} & Nominal voltage & 330 V
		\NN & Electric charge & 50 Ah
		\NN & Theoret. energy & 16500 Wh
		\NN & Mass & 165 kg
		\NN & Energy density & 100 Wh/kg
		\ML \multirow{3}*{Motor data} & Typ & Permanent Synchronous Motor
		\NN & Nominal power & 35 kW
		\NN & max. Torque & 180 Nm
		\LL}
```

![Table](https://s3.amazonaws.com/zeMirco/github/latex-template/table.png)

## Equations

The big advantage of LaTex is how nicely complex equations are handled.

Equation for extraterrestrial radiation. Taken from **Renewable and Efficient Electric Power Systems** by Gilbert M. Masters on page 432, 7.43.

```
\begin{equation}
  \glsentrytext{I0} = \frac{24}{\pi} \glsentrytext{SC} \left[1+0,034\cos\left(\frac{360\glsentrytext{n}}{365}\right)\right](\cos \glsentrytext{L} \cos \glsentrytext{delta} \sin \glsentrytext{HSR} + \glsentrytext{HSR} \sin \glsentrytext{L} \sin \glsentrytext{delta})
\end{equation}
```

Equation for average wind power. Taken from **Betrieb von Kleinwindkraftanlagen - ein Überblick über Markt, Technik und Wirtschaftlichkeit** by W. Halbhuber on page 95.

```
\begin{equation}
	\overline P_w = \frac{c_1}{T} \int_0^T v_w^3\,dt \ne c_1 \left(\frac{1}{T}\int_0^T v_w\,dt\right)^3 = c_1 \cdot \overline{v}_w^3.
\end{equation}
```

![Equations](https://s3.amazonaws.com/zeMirco/github/latex-template/equations.png)

## List of acronyms

```
\newacronym{PVGIS}{PVGIS}{Photovoltaic Geographical Information System}
```
Before
![Acronyms without style](https://s3.amazonaws.com/zeMirco/github/latex-template/acronyms_without_style.png)

After
![Acronyms with style](https://s3.amazonaws.com/zeMirco/github/latex-template/acronyms_with_style.png)

## List of symbols

```
\newglossaryentry{IDC}{name=\ensuremath{\bar I_{\textnormal{DC}}}, symbol={kWh/m\ensuremath{^2} pro Tag}, description={Durchschnittliche diffuse Sonneneinstrahlung auf eine Kollektoroberfläche}, type=symbolslist}
```

## Beautiful graphs

### Line graph

![Line graph](https://s3.amazonaws.com/zeMirco/github/latex-template/line_graph.png)


### Bar charts

![Simple bar chart](https://s3.amazonaws.com/zeMirco/github/latex-template/simple_bar_chart.png)


### Stacked bar charts

![Stacked bar chart](https://s3.amazonaws.com/zeMirco/github/latex-template/stacked-bar-chart.png)

### Pie charts

![Pie chart](https://s3.amazonaws.com/zeMirco/github/latex-template/pie_chart.png)

### Two y-axes

![Two y-axes](https://s3.amazonaws.com/zeMirco/github/latex-template/two_y_axes.png)

## Text replacement

Before
![Without text replacement](https://s3.amazonaws.com/zeMirco/github/latex-template/psfrag_without.png)

After
![Text replacement](https://s3.amazonaws.com/zeMirco/github/latex-template/psfrag.png)

## Electronic circuits

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

![Electronic circuits](https://s3.amazonaws.com/zeMirco/github/latex-template/electronic_circuits.png)

## Custom bibliography

Before
![Custom bib before](https://s3.amazonaws.com/zeMirco/github/latex-template/bib-before.png)

After
![Custom bib after](https://s3.amazonaws.com/zeMirco/github/latex-template/bib-after.png)

```
\usepackage[style=numeric, firstinits=true, backend=bibtex]{biblatex}
\urlstyle{same}
\DeclareFieldFormat{title}{#1\isdot}
\renewcommand{\labelnamepunct}{\addcolon\space}
\renewcommand{\multinamedelim}{\addsemicolon\space}
\renewcommand{\finalnamedelim}{\addsemicolon\space}
\DeclareNameFormat{default}{\usebibmacro{name:last-first}{#1}{#4}{#5}{#7}\usebibmacro{name:andothers}}
\DefineBibliographyStrings{ngerman}{urlseen={abgerufen am}}

\bibliography{bibliography/bibliography}
```
## Acknowledgements

Clemens v. Loewenich and Johannes Werner for creating the tud classes.