<div align="center">

# ✦ Lumina

**An eye-candy LaTeX theme for lecture notes, reports, and theses**

[![License](https://img.shields.io/github/license/sohamch08/lumina?style=for-the-badge&color=5E81AC)](LICENSE)
[![LaTeX](https://img.shields.io/badge/LaTeX-pdfLaTeX-008080?style=for-the-badge&logo=latex&logoColor=white)](https://www.latex-project.org/)
[![Stars](https://img.shields.io/github/stars/sohamch08/lumina?style=for-the-badge&color=EBCB8B)](https://github.com/sohamch08/lumina/stargazers)

</div>

---

## Previews

<img width="49%" src="images/preview-1.png"> <img width="49%" src="images/preview-2.png">

---

## Showcase

Lumina was used to typeset my MSc project report at TIFR, Mumbai:

> **[Exponential Sums and Weil Bounds](https://github.com/sohamch08/msc-project-tifr)** — a survey of character sum theory, elementary proofs of the Weil bounds, and Kopparty's decoding algorithms for codes constructed from character evaluations.

[![MSc Project](https://img.shields.io/badge/MSc%20Project-TIFR%20Mumbai-2D4889?style=for-the-badge&logo=latex&logoColor=white)](https://github.com/sohamch08/msc-project-tifr)
[![PDF](https://img.shields.io/badge/PDF-View%20Report-red?style=for-the-badge&logo=adobeacrobatreader&logoColor=white)](https://github.com/sohamch08/msc-project-tifr/blob/master/msc-project.pdf)

---

## Title Pages

Two custom title pages — `\mytitlea` (orange geometric) and `\mytitleb` (diagonal bands):

<img width="49%" src="images/title-1.png"> <img width="49%" src="images/title-2.png">

```tex
\begin{document}
\thispagestyle{empty}
\mytitleb{Title Here}{Soham Chatterjee}{sohamchatterjee999@gmail.com}{2024}
\newpage
...
\end{document}
```

> `\mytitleb{Title}{Author}{Email}{Year}` — use inside `\begin{document}`, before `\maketitle`. Add `\thispagestyle{empty}` and `\newpage` around it.

---

## Theorem Environments

Color-coded boxes for every mathematical environment:

| Environment | Color | Short command |
|---|---|---|
| Theorem | Blue | `\thm[ref]{Title}{Body}` |
| Lemma | Green | `\lem[ref]{Title}{Body}` |
| Claim | Green | `\clm[ref]{Title}{Body}` |
| Corollary | Purple | `\cor[ref]{Title}{Body}` |
| Definition | Red | `\dfn[ref]{Title}{Body}` |
| Example | Teal | `\ex[ref]{Title}{Body}` |
| Open Question | Purple | `\opn[ref]{Title}{Body}` |

<img width="100%" src="images/theorem%20boxes.png">

Each environment has **two variants**: one numbered within sections (lowercase name, e.g. `lemma`) and one numbered within chapters (capitalized name, e.g. `Lemma`). The short commands above use the section variant by default; append `c` for the chapter variant (`\lemc`, `\corc`, `\thmc`, …).

---

## Referencing

Every environment produces a label prefixed by its type. Pass the ref name as the optional `[ref]` argument:

```tex
\thm[ftc]{Fundamental Theorem of Calculus}{Statement here.}
% refer elsewhere as: \ref{th:ftc}
% or with custom text: \hyperref[th:ftc]{Theorem \ref{th:ftc}}
```

| Environment | Prefix |
|---|---|
| Theorem / Claim / Lemma / Corollary | `th:` |
| Definition / Exercise / Open Question | `def:` |
| Example | `ex:` |
| Question | `qs:` |

---

## Proof Environments

The proof environment is multipurpose — use the first argument to name what you're writing:

```tex
\pf{Proof}{...}
\pf{Proof Idea}{...}
\pf{Proof Overview}{...}
\pf{Proof Sketch}{...}
```

---

## Contents Page

A styled table of contents using TikZ:

<img width="100%" src="images/contents.png">

> Avoid adjusting the page margins — the ToC layout depends on them.

---

## Macros

### Letter Fonts — [`letterfonts.tex`](letterfonts.tex)

```tex
\bbA   % Blackboard Bold  (\mathbb{A})
\bmA   % Bold Math        (\boldsymbol{A})
\sA    % Script           (\mathscr{A})
\mfA   % Fraktur          (\mathfrak{A})

\ovA   % Overline         (\overline{A})
\tdA   % Tilde            (\tilde{A})
\vA    % Vector           (\vec{A})
```

Greek shorthand: `\al` `\gm` `\dl` `\eps` `\veps` `\lm` `\sg` `\vph` `\om` (and their capitals).

### General Macros — [`macros.tex`](macros.tex)

Common shorthands for analysis, algebra, and combinatorics — see the file for the full list.

---

## Files

| File | Purpose |
|---|---|
| [`preamble.tex`](preamble.tex) | Core theme — colors, theorem boxes, ToC, title pages |
| [`preamble-article.tex`](preamble-article.tex) | Article variant (no chapters) |
| [`preamble-formal.tex`](preamble-formal.tex) | Formal/report variant |
| [`letterfonts.tex`](letterfonts.tex) | Font shorthands |
| [`macros.tex`](macros.tex) | Math macros |
| [`main.tex`](main.tex) | Minimal working example |
