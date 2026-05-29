<div align="center">

<br>

# ✦ &ensp; L U M I N A

<br>

> *Beautiful mathematics deserves beautiful typography.*

**An eye-candy LaTeX theme for lecture notes, reports, and theses**

<br>

[![LaTeX](https://img.shields.io/badge/engine-pdfLaTeX-008080?style=for-the-badge&logo=latex&logoColor=white&labelColor=1C1C2E)](https://www.latex-project.org/)&ensp;[![Stars](https://img.shields.io/github/stars/sohamch08/lumina?style=for-the-badge&color=EBCB8B&labelColor=1C1C2E)](https://github.com/sohamch08/lumina/stargazers)&ensp;[![Demo PDF](https://img.shields.io/badge/demo-main.pdf-BF616A?style=for-the-badge&labelColor=1C1C2E&logo=adobeacrobatreader&logoColor=white)](main.pdf)

<br>

</div>

◆&ensp;**Color-coded theorem boxes** &nbsp;—&nbsp; 7 environments, section & chapter variants  
◆&ensp;**Gradient cover pages** &nbsp;—&nbsp; per-document identity from one config file  
◆&ensp;**TikZ-powered table of contents** &nbsp;—&nbsp; accent-unified with chapter bars  
◆&ensp;**Smart ref macros** &nbsp;—&nbsp; hyperlinked `\thmref`, `\lemref`, `\defref`, …  
◆&ensp;**10+ proof environments** &nbsp;—&nbsp; sketch · idea · alternate · combinatorial · algebraic  
◆&ensp;**Two-sided headers** &nbsp;—&nbsp; chapter mark on right pages, section mark on left

---

## ◈ &ensp; Previews

<div align="center">

<img width="49%" src="images/preview-1.png"> <img width="49%" src="images/preview-2.png">

</div>

---

## ◈ &ensp; Demo

The file [`main.tex`](main.tex) is a fully worked example using the theme. Two chapters of Greek mathematics covering commensurability, irrationality, and prime numbers. The compiled output is [`main.pdf`](main.pdf).

---

## ◈ &ensp; Showcase

Lumina has been used to typeset several lecture note sets and a full MSc thesis at TIFR Mumbai:

<table>
<tr>
<td><b>Exponential Sums and Weil Bounds</b> &mdash; MSc project report (TIFR)</td>
<td><a href="https://github.com/sohamch08/msc-project-tifr"><img src="https://img.shields.io/badge/msc--project--tifr-5E81AC?style=for-the-badge&logo=github&logoColor=white&labelColor=1C1C2E"></a></td>
</tr>
<tr>
<td><b>Algorithms</b> (CSS.201.1, TIFR 2024)</td>
<td><a href="https://github.com/sohamch08/algorithms-tifr"><img src="https://img.shields.io/badge/Algorithms--TIFR-5E81AC?style=for-the-badge&logo=github&logoColor=white&labelColor=1C1C2E"></a></td>
</tr>
<tr>
<td><b>Complexity, Coding Theory, and more</b></td>
<td><a href="https://github.com/sohamch08/Academic-Notes"><img src="https://img.shields.io/badge/Academic--Notes-5E81AC?style=for-the-badge&logo=github&logoColor=white&labelColor=1C1C2E"></a></td>
</tr>
<tr>
<td><b>Multivariable Analysis</b></td>
<td><a href="https://github.com/sohamch08/multivariable-analysis-CMI"><img src="https://img.shields.io/badge/Multivariable--Analysis-5E81AC?style=for-the-badge&logo=github&logoColor=white&labelColor=1C1C2E"></a></td>
</tr>
</table>

---

## ◈ &ensp; Title Page

The gradient cover is built from two files: `title.tex` (the template never needs editing) and `config.tex` (your per-document settings). **Only `config.tex` needs to be edited.** Fill in your details and the cover builds itself.

<details>
<summary><b> config.tex: full template</b></summary>

<br>

```tex
% config.tex

% Cover gradient (top → bottom)
\definecolor{covercolorone}{HTML}{E64C4C}   % top color
\definecolor{covercolortwo}{HTML}{1B2021}   % bottom color

% TOC & chapter heading accent (see Contents Page section)
\definecolor{mytoccolor}{HTML}{4549C4}

% Course / document info
\newcommand{\coursetitle}{Your Course Name}
\newcommand{\courseyear}{Institution, Year}
\newcommand{\instructor}{}              % leave empty to hide the Instructor line

% Scribe / author info
\newcommand{\scribename}{Your Name}
\newcommand{\scribeemail}{you@institution.edu}
\newcommand{\scriberwebsite}{https://yourwebsite.com/}  % leave empty to hide
\newcommand{\scriberwebsitetext}{yourwebsite.com}

% Git footer
\renewcommand{\gitrepo}{yourname/yourrepo}
```

</details>

<details>
<summary><b> main.tex: minimal setup</b></summary>

<br>

Then in your main file, load config before `\begin{document}` and drop `\input{title}` where the cover should appear:

```tex
\input{preamble}
\input{macros}
\input{letterfonts}
\input{config}          % ← edit this file only

\begin{document}
\input{title}           % ← renders the cover page automatically
…
\end{document}
```

</details>

Different gradient colors give each document its own identity:

<table width="100%">
<tr>
<td align="center" width="25%"><img src="images/cover-algorithms.png" width="100%"><br><sub><b>Algorithms</b></sub></td>
<td align="center" width="25%"><img src="images/cover-coding-theory.png" width="100%"><br><sub><b>Topics in Coding Theory</b></sub></td>
<td align="center" width="25%"><img src="images/cover-mfcs.png" width="100%"><br><sub><b>Math Foundations of CS</b></sub></td>
<td align="center" width="25%"><img src="images/cover-agt.png" width="100%"><br><sub><b>Algorithmic Game Theory</b></sub></td>
</tr>
</table>

---

## ◈ &ensp; Theorem Environments

Color-coded boxes for every mathematical environment. Theorem body text is set in italic by default.

| Environment | Color | Section variant | Chapter variant |
|---|---|---|---|
| Theorem | Blue | `\thm[ref]{Title}{Body}` · `theorem` | `\thmc[ref]{Title}{Body}` · `theoremCh` |
| Lemma | Green | `\lem[ref]{Title}{Body}` · `lemma` | `\lemc[ref]{Title}{Body}` · `lemmaCh` |
| Claim | Green | `\clm[ref]{Title}{Body}` · `claim` | `\clmc[ref]{Title}{Body}` · `claimCh` |
| Corollary | Purple | `\cor[ref]{Title}{Body}` · `corollary` | `\corc[ref]{Title}{Body}` · `corollaryCh` |
| Definition | Red | `\dfn[ref]{Title}{Body}` · `definition` | `\dfnc[ref]{Title}{Body}` · `definitionCh` |
| Example | Teal | `\ex[ref]{Title}{Body}` · `example` | `\exc[ref]{Title}{Body}` · `exampleCh` |
| Open Question | Purple | `\opn[ref]{Title}{Body}` · `openq` | `\opnc[ref]{Title}{Body}` · `openqCh` |

<img width="100%" src="images/theorem boxes.png">

Section variants are numbered within sections (`theorem`, `lemma`, …); chapter variants within chapters (`theoremCh`, `lemmaCh`, …). The short commands follow the same pattern — append `c` for the chapter variant (`\thmc`, `\lemc`, `\corc`, …).

---

## ◈ &ensp; Referencing

All ref macros and proof-alignment helpers live in `preamble.tex`. Pass the ref name as the optional `[ref]` argument:

| Environment | Prefix | Ref macro |
|---|---|---|
| Theorem | `th:` | `\thmref` |
| Lemma | `th:` | `\lemref` |
| Corollary | `th:` | `\corref` |
| Claim | `th:` | `\claimref` |
| Proposition | `th:` | `\propref` |
| Definition / Exercise / Open Question | `def:` | `\defref` |
| Observation | (raw) | `\obsref` |
| Example | `ex:` | — |

All ref macros accept an optional suffix: `\thmref[s]{ftc}` → "Theorem 1.1s".

<details>
<summary><b> Declaring & referencing environments</b></summary>

<br>

```tex
\thm[ftc]{Fundamental Theorem of Calculus}{Statement here.}
% refer elsewhere as \thmref{ftc}   →  "Theorem 1.1"
% or with link text: \hyperref[th:ftc]{Theorem \ref{th:ftc}}
```

</details>

<details>
<summary><b> \by family — proof step annotations</b></summary>

<br>

Use inside `align` environments to annotate proof steps:

```tex
\by{Theorem 1.1}      % &[By Theorem 1.1]
\byt{ftc}             % &[By Theorem 1.1]   (auto-linked via \thmref)
\byl{key}             % &[By Lemma X.X]
\byc{key}             % &[By Corollary X.X]
\byo{key}             % &[By Observation X]
\bye{eq-label}        % &[By (X.X)]          (equation ref)
```

</details>

---

## ◈ &ensp; Proof Environments

<details>
<summary><b> All proof environments</b></summary>

<br>

```tex
\begin{proof}...\end{proof}
\begin{proof-sketch}...\end{proof-sketch}
\begin{proof-idea}...\end{proof-idea}
\begin{proof-attempt}...\end{proof-attempt}
\begin{alternate-proof}...\end{alternate-proof}
\begin{anotherproof}...\end{anotherproof}
\begin{combi-proof}...\end{combi-proof}     % Combinatorial Proof
\begin{alg-proof}...\end{alg-proof}         % Algebraic Proof
\begin{proofmany}[2]...\end{proofmany}      % Proof 2 / Proof (ii) etc.
\begin{want}...\end{want}                   % Want: ...
\begin{enough}...\end{enough}               % Enough to Show: ...
```

</details>

---

## ◈ &ensp; Contents Page

A styled table of contents using TikZ. The chapter heading color and the ToC color are unified — both driven by `mytoccolor`, which is set in `config.tex`. Changing that one color updates the chapter title bar, all ToC entries, and section numbers throughout the document.

<img width="100%" src="images/contents-algo.png">

> Avoid adjusting the page margins — the ToC layout depends on them.

---

## ◈ &ensp; Macros

<details>
<summary><b> Letter Fonts &nbsp;—&nbsp; <a href="letterfonts.tex"><code>letterfonts.tex</code></a></b></summary>

<br>

```tex
\bbA   % Blackboard Bold  (\mathbb{A})
\bmA   % Bold Math        (\boldsymbol{A})
\sA    % Script           (\mathscr{A})
\mfA   % Fraktur          (\mathfrak{A})
\mcA   % Calligraphic     (\mathcal{A})
\ovA   % Overline, \tdA tilde, \vcA vec, \hA widehat
```

Greek shorthand: `\al` `\gm` `\dl` `\eps` `\veps` `\lm` `\sg` `\vph` `\om` (and their capitals).

</details>

<details>
<summary><b> General Macros &nbsp;—&nbsp; <a href="macros.tex"><code>macros.tex</code></a></b></summary>

<br>

```tex
\Leg{a}{p}                % Legendre symbol (a/p)
\Tfae                     % "The following are equivalent:"
\quotient{G}{H}           % G / H  (inline quotient)
\matr{a & b \\ c & d}     % matrix without brackets
\ctr                      % contradiction lightning bolt  (requires marvosym)
\ov{x}                    % \overline{x}
\del{f}{x}                % partial derivative ∂f/∂x
\mat{a & b \\ c & d}      % matrix with brackets
\comb{n}{k}               % binomial coefficient
```

</details>

---

## ◈ &ensp; Files

| File | Purpose |
|---|---|
| [`preamble.tex`](preamble.tex) | Core theme — colors, theorem boxes, ref macros, proof-alignment helpers, ToC, title formats |
| [`preamble-article.tex`](preamble-article.tex) | Article variant (no chapters) |
| [`preamble-formal.tex`](preamble-formal.tex) | Formal/report variant |
| [`letterfonts.tex`](letterfonts.tex) | Font shorthands |
| [`macros.tex`](macros.tex) | Math macros |
| [`config.tex`](config.tex) | **Per-document settings** — gradient colors, `mytoccolor`, title, author, git repo |
| [`title.tex`](title.tex) | Cover page template (reads from `config.tex`, no editing needed) |
| [`main.tex`](main.tex) | Minimal working example |

<br>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:4549C4,50:1C1C2E,100:0B0C1A&height=120&section=footer"/>
