Allergy: Writing drafts in LaTeX
=================================

I always find myself loading the same basic packages over and over again in all my notes and articles.  Over the years, the loaded packages have stabilised into what is now `allergy.sty`.  It can be used with different options at the three production stages of any document, the *drafting*, *review* and *publication* stages.

A typical use case at **draft stage** is

```latex
\documentclass{scrartcl}

\usepackage[watermark, showeqnr, theoremdefs]{allergy}

\begin{document}
Here is an equation without reference, but nevertheless numbered with the \texttt{showeqnr} option on:
\begin{align}
f \colon A \to B
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

Some extra math delimiter commands are defined such as \(\abs{x}\), \(\norm{x}\), or \(\pairing{\omega}{X}\).
Sets can be defined as \(S \coloneqq \set{1,2,\ldots}\), or by comprehension as \(S' \coloneqq \setc{i \in S}{i \leq 10}\).

There is also a nice watermark on the top of every page (compile several times).

\itodo[Me]{Here is an inline todo of some urgent issue to address}

\itodo*[Me]{Another, less urgent task, with the starred version of the \texttt{itodo} command.}
```

When the document is in **review stage**, add the `final` option, and remove the `watermark` option:

```latex
\usepackage[final, showeqnr, theoremdefs]{allergy}
```

At **publication stage**, you may want to remove `showeqnr` so that only referred equations are numbered, as is customary in most journals:
```latex
\usepackage[final, theoremdefs]{allergy}
```

Here is a brief list of options with their meaning:

* `final`: Remove todos, and margin labels
* `showeqnr`: Show all equation numbers (you should use the unstarred `align`, or `equation` environment in your draft)
* `biblatex`: Load biblatex with some reasonable defaults
* `watermark`: Add a watermark with a timestamp on top of every page
* `theoremdefs`: Add standard theorem definitions

See [my blog post about LaTeX](https://www.olivierverdier.com/posts/2013/07/15/modern-latex/) for more details, and tips on how to use LaTeX at its best.
