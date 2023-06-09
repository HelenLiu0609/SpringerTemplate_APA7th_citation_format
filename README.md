# APA (7th ed.) Citation/Bibliography Style with Springer Template

This repository provides an APA (7th ed.) citation and bibliography style specifically modified for the Springer template. The style is modified to ensure proper formatting and adherence to the guidelines outlined in the Publication Manual of the American Psychological Association (7th edition).

## Usage

To use this citation style in your LaTeX document, follow the instructions below:

1. Download the zip file from this repository.
2. Follow the instruction in the first section.
In your LaTeX document, use the following commands for citations:

- Use `\parencite{label}` for citation style `(name, year)`.
- Use `\textcite{label}` for citation style `name (year)`.

## Modification Details

The official template uses `\documentclass[xxx]{sn-jrl}` with the corresponding `xxx.bst` file from the bst folder to denote with reference style you use. Since it cannot directly provide APA (7th ed.) style, some modification is needed. This template follows the following steps:

1. Choose `\documentclass[sn-apa]{sn-jrl}` in the beginning of the file `sn-article.tex`. (You can also choose other document classes)
2. Open the file `sn-jnl.cls` and comment all the lines after `\if@APA@refstyle%` (related to the chosen document class in the first step) like this: 
```
\if@APA@refstyle%
%\if@Numbered@refstyle%
%%  \usepackage[natbibapa]{apacite}%
%  \gdef\NumBib{YES}%
%\else%
%%  \usepackage[natbibapa]{apacite}%
%  \gdef\NumBib{NO}%
%\fi%
%  \bibliographystyle{apacite}%
%  \def\refdoi#1{\urlstyle{rm}\url{#1}}%
%  \renewcommand{\doiprefix}{}%
%  \AtBeginDocument{%
%    \renewcommand{\BPBI}{.}% Period between initials - command from apacite.sty
%  }%
%  \setlength{\bibsep}{1em}%
%  \def\bibfont{\reset@font\fontfamily{\rmdefault}\normalsize\selectfont}%
%\fi%
```
3. Add the following usepackages in the head of `sn-article.tex`:
```
\usepackage[utf8]{inputenc}
\usepackage[style=apa, backend=biber]{biblatex}
\addbibresource{sn-bibliography.bib}
```
4. Add `\printbibliography` at the end of the main body before \end{document} for printing bibliography and delete (or comment) `\bibliography{sn-bibliography}`.

## Compatibility

The provided APA citation style works well in overleaf with the latest Tex Live version. If you are editing your manuscript offline on your own PC/Mac, make sure your installed Tex Live version is up to date.
