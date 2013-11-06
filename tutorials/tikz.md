# Using TikZ with LaTeXing

[`TikZ`][tikz] is together with PGF a TeX package for creating graphics
programmatically. TikZ is build on top of PGF and allows you to create
sophisticated graphics in a rather intuitive and easy manner. `LaTeXing` makes
it more comfortable and faster to use `TikZ` in Sublime Text 3. In this
tutorial the setup process and the individual configuration possibilities are
covered.

Let's consider an example before we talk about the setup in detail.

	\documentclass{article}
	\usepackage[utf8]{inputenc}

	\usepackage{tikz}

	\begin{document}

	\begin{tikzpicture}[scale=.8, z={(-.707,-.3)}]
	  \draw (4,0,0) -- (0,0,0) -- (0,5,0);
	  \draw (4,0,0) -- (4,0,-3) -- (4,5,-3) -- (4,5,0) -- cycle;
	  \draw (4,5,0) -- (0,5,0) -- (0,5,-3) -- (4,5,-3);
	  \draw[style=dashed, color=gray] (4,0,-3) -- (0,0,-3) -- (0,5,-3);
	  \draw[style=dashed, color=gray] (0,0,0) -- (0,0,-3);
	  \draw (2,-.4,0) node{4 ft};
	  \draw (4.6,-.2,-1.5) node{3 ft};
	  \draw (4.5,2.5,-3) node{5 ft};
	\end{tikzpicture}

	\end{document}

which will create the following [pdf file][tikz_example1]. This is a very
basic example and not taking any advantage of using LaTeXing so far.

## How to use TikZ

There are two packages for Sublime Text 3:

1. [TikZ][sublime_tikz] provides syntax highlighting and snippets for TikZ.
2. Our very own [LaTeXing][latexing] handles `TikZ` files just like regular
   `LaTeX` files. Simply hit `ctrl+b` (or `super+b` on a OSX) to build.

The easiest way to install these plugins is to get [Package Control][pc],
bring up the command palette (`strg+shift+p` on Windows and Linux,
`super+shift+p` on the OSX), select `Package Control: Install Package`, select
the package you want, and hit enter. You can easily get things up and running
in three minutes or less.

To enable `tikz` support in `LaTeXing` you only have to add a single option to
your LaTeXing settings: (In the menu select Preferences/Package
Settings/LaTeXing/Settings - User and insert the following line.)

	"tikz": true,
	"tikz_create_pdf": true

The second option is optional, you can also leave it off, the purpose will be
explained later in this tutorial. Now, just copy the sample tikzpicture above,
paste it into a new file, and save it as `demo1.tikz` in a folder of your
liking

	% -*- root: Document.tex -*-
	\begin{tikzpicture}[scale=.8, z={(-.707,-.3)}]
	  \draw (4,0,0) -- (0,0,0) -- (0,5,0);
	  \draw (4,0,0) -- (4,0,-3) -- (4,5,-3) -- (4,5,0) -- cycle;
	  \draw (4,5,0) -- (0,5,0) -- (0,5,-3) -- (4,5,-3);
	  \draw[style=dashed, color=gray] (4,0,-3) -- (0,0,-3) -- (0,5,-3);
	  \draw[style=dashed, color=gray] (0,0,0) -- (0,0,-3);
	  \draw (2,-.4,0) node{4 ft};
	  \draw (4.6,-.2,-1.5) node{3 ft};
	  \draw (4.5,2.5,-3) node{5 ft};
	\end{tikzpicture}


The only thing what you have to do in this file is to connect it with the root
document to load the preambles. This makes it very easy to keep the same style
across all you figures. `Document.tex` should look like this:

	\documentclass{article}
	\usepackage[utf8]{inputenc}

	\usepackage{tikz}

	\begin{document}

	\includegraphics{demo1.pdf}

	\end{document}

LaTeXing will automatically detect all preambles until `\\begin{document}`.
You can further adjust this by defining `% (TIKZ)` somewhere in you main
document and just everything until this stop mark will included. The use of `%
(TIKZ)` is sometimes handy if you don't need all preambles to load for a tikz
picture.

Let's go back to `demo1.tikz`, hit `ctrl+b` (or `super+b` on a OSX) to creates
a preview of just the current [picture][tikz_example2] and saves it as pdf
next to the tikz picture if the option is enabled. From now on you can just
include the pdf like a usual figure, this help a lot while using a lot of tikz
pictures to avoid long typeset processes.

## TikZ Live Preview

The `TikZ` support also included a live preview mode which will automatically
build your figure shortly after your last modification. Just call "LaTeXing:
Toggle TikZ Live Preview" being in your .tikz file.

The [TikZ website][tikz] is a good place to find out more about tikz's
features. It provides a number of [examples][tikz_demos] that will get you
started on the basics.

[tikz]: http://www.texample.net/tikz/
[tikz_demos]: http://www.texample.net/tikz/examples
[tikz_example1]: files/tikz_example1.pdf
[tikz_example2]: files/tikz_example2.pdf
[tikz_example3]: files/tikz_example3.pdf
[knitr_options]: http://yihui.name/knitr/options
[sublime_tikz]: https://github.com/Chris---/SublimeText-TikZ
[latexing]: http://www.latexing.com/
[pc]: https://sublime.wbond.net/installation
