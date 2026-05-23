# Lumina Theme
**Lumina** is an eye-candy LaTeX theme for lecture notes, reports, and thesis writing. If you want to check an actual example using Lumina, take a look at my [Analysis Lecture Notes](analysis_class-note.pdf). If you want to just view some pages, here are some previews.

<img width=100% src="images/preview-1.png">
<img width=100% src="images/preview-2.png">


## Title Page
There are two custom title pages. I have named them `\mytitlea` and `\mytitleb`. Among them I have used the `\mytitleb` in the analysis lecture notes.

<img  width=100% src="images/title-1.png">
<img  width=100% src="images/title-2.png">

The command goes like this
```tex
\mytitleb{Title}{Author}{Email}{Year}
```
>- Use this command inside the `\begin{document}`.
>- Do not use the usual `\maketitle` process here ie you first wrote the `title{}` `\author{}` and `\date{}` then inside the `\begin{document}`, `\maketitle`.
>- I would recommend first add `\thispagestyle{empty}` to make the title page without pagenumber. And after the `\mytitleb` command add a `\newpage` to make a forcefull page break.

So the whole command block looks like this
```tex
\begin{document}
	
\thispagestyle{empty}
\mytitleb{Title Here}{Soham Chatterjee}{sohamchatterjee999@gmail.com}{2021}
\newpage
...
Put your content here
...
\end{document}
```

## Theorem Boxes
I have many theorem boxes for Theorems, Corollaries, Lemmas, Claims, Definitions, Examples, Questions etc.

<img  width=100% src="images/theorem%20boxes.png"> 

The environments which are appears in pairs one of them is for the chapters which have sections whose environment name starts with small letter and the other is for chapters which do not have sections whose environment name starts with capital letter. In the short command for the latter I used the letter 'c' to represent it should be use if it is not under a section

Short commands for environments goes like this
```tex
\commandName[reference_name]{heading}{description}
```
For example in theorem for suppose Fundamental Theorem of Calculus i will write like this
```tex
\thm[ftc]{Fundamental Theorem of Calculus}{Theorem Statement}
```
## Referencing Theorems
Take the code for the `Theorem` box
```tex
\tcbuselibrary{theorems,skins,hooks}
\newtcbtheorem[number within=section]{Theorem}{Theorem}
{%
	enhanced,
	breakable,
	colback = mytheorembg,
	frame hidden,
	boxrule = 0sp,
	borderline west = {2pt}{0pt}{mytheoremfr},
	sharp corners,
	detach title,
	before upper = \tcbtitle\par\smallskip,
	coltitle = mytheoremfr,
	fonttitle = \bfseries\sffamily,
	description font = \mdseries,
	separator sign none,
	segmentation style={solid, mytheoremfr},
}
{th}
```
Here take the last `{th}` term in mind cause this will be used in referencing. Suppose a use case of theorem

```tex
\begin{Theorem}{title}{refer}
  Theroem Statement
	...
\end{Theorem}
```
To refer this in another place use the command `\ref{th:refer}`. This will put `(1.1.1)` type of text with a link to that theorem in your document. To use custom text for example I want to put `Theorem 1.1.1` and then use the command

```tex
\hyperref[th:refer]{Theorem \ref{th:refer}}
```
This will do the work. This process will work for all the theorem boxes I have defined. Here are the terms to be used in each type of theorem boxes

```
Theorem:		th
Claim:			th
Lemma:			th
Corollary:		th
Definition:		def
Example:		ex
Question:		qs
Exercise:		def
Open Question:		def
```


## Proof
The proof environment actually multipurpose. For a proof many things actually play. Proof idea. Proof overview. Main pproof. Proof prerequisites etc. Thats why the first option uses the actual name of what exactly we are writing for the proof. It will go like this
Proof idea: `\pf{Proof Idea}{content..}`
Proof Overview: `\pf{Proof Overview}{content..}`
Proof : `\pf{Proof}{content..}`

>Thereom boxes, Proof environment, Title pages and contents page are set up in the file [preamble](preamble.tex)

## Contents Page
I have a beautiful looking contents page. 

<img  width=100% src="images/contents.png">

>I woulld suggest dont play with the margin. It kind of ruins the contents page.


## Macros
I have two macros file. One is for different fonts and the hats, bars, tildes. These are in [letterfonts](letterfonts.tex) file. 
```tex
Blackboard Font:              \newcommand{\bbA}{\mathbb{A}}
Bold Math:                    \newcommand{\bmA}{\boldsymbol{A}}
Math SCR Font:                \newcommand{\sA}{{\mathscr{A}}}
Math Fraktur Font:            \newcommand{\mfA}{\mathfrak{A}}


Bar:                          \newcommand{\ovA}{\overline{A}}
Tilde:                        \newcommand{\tdA}{\tilde{A}}
Vector:                       \newcommand{\vA}{\vec{A}}


Greek Letters:
\newcommand{\al}{\alpha}		  \newcommand{\Al}{\Alpha}
\newcommand{\gm}{\gamma}		  \newcommand{\Gm}{\Gamma}
\newcommand{\dl}{\delta}		  \newcommand{\Dl}{\Delta}
\newcommand{\eps}{\epsilon}		\newcommand{\Eps}{\Epsilon}    \newcommand{\veps}{\varepsilon}
\newcommand{\lm}{\lambda}		  \newcommand{\Lm}{\Lambda}
\newcommand{\sg}{\sigma}		  \newcommand{\Sg}{\Sigma}

\newcommand{\vph}{\varphi}
\newcommand{\om}{\omega}		  \newcommand{\Om}{\Omega}
```

There are some other macros for general use in lecture notes, reports, and thesis documents. These are in the file [macros](macros.tex).
