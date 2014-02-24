LatexDev: Writing drafts in LaTeX
=================================

A LaTeX style file to write drafts (and final documents) in LaTeX.

A typical use case at *draft stage* is

```latex
\documentclass{scrartcl}

\usepackage[watermark, showeqnr, theoremdefs]{latexdev}

\begin{document}
Here is an equation without reference, but nevertheless numbered with the \texttt{showeqnr} option on:
\begin{align}
x = 3
\end{align}

Here is a labeled equation, with label visible in the margin:
\begin{align}
\label{eq:important}
2 + 2 = 4
\end{align}

The following holds
\begin{theorem}
Sensible theorem, lemma and definition environments are already defined.
\end{theorem}

There is also a nice watermark on the top of every page (compile several times).

\itodo[Me]{Here is an inline todo of some urgent issue to address}
```

When the document is in *review stage*, add the `final` option, and remove the `watermark` option:

```latex
\usepackage[final, showeqnr, theoremdefs]{latexdev}
```

At *publication stage*, you may want to remove `showeqnr` so that only referred equations are numbered, as is customary in most journals:
```latex
\usepackage[final, theoremdefs]{latexdev}
```

Here is a brief list of options with their meaning:

* `final`: Remove todos, and margin labels
* `showeqnr`: Show all equation numbers (you should use the unstarred `align`, or `equation` environment in your draft)
* `biblatex`: Load biblatex with some reasonable defaults
* `watermark`: Add a watermark with a timestamp on top of every page
* `theoremdefs`: Add standard theorem definitions

See [my blog post about LaTeX](http://www.olivierverdier.com/posts/2013/07/15/modern-latex/) for more details, and tips on how to use LaTeX at its best.
