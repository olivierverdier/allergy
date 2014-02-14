LatexDev: Writing drafts in LaTeX
=================================

A LaTeX style file to write drafts (and final documents) in LaTeX.

A typical use case while writing the draft is

```latex
	\usepackage[watermark, showeqnr, theoremdefs]{latexdev}
```

When the document is in final stage, add the `final` option

```latex
	\usepackage[final, watermark, showeqnr, theoremdefs]{latexdev}
```

Here is a brief list of options with their meaning:

* `final`: Remove watermark, todo, and keys 
* `showeqnr`: Show all equation numbers (you should use the unstarred `align`, or `equation` environment in your draft)
* `biblatex`: Use biblatex
* `watermark`: Add a watermark with a timestamp
* `theoremdefs`: Add standard theorem definitions

See [my blog post about LaTeX](http://www.olivierverdier.com/posts/2013/07/15/modern-latex/) for more details, and tips on how to use LaTeX at its best.
