# Using knitr with LaTeXing

[`knitr`][knitr] is a syntax and an `R` package that allow you to put `R` code right in your LaTeX files. This is great for writing scientific articles or reports that use data, because you never loose track of how exactly you arrived at your results. `LaTeXing` makes it dead simple to use `knitr` in Sublime Text 3. In this post I would like to introduce you to my `knitr` setup.

Let's consider an example before we talk about the setup in detail.

	\documentclass{article}

	\begin{document}

	R can be used as a calculator.

	<<calc>>=
	5 + 5
	@

	Knitr integrates R plots into your document.

	<<plot_something, fig.width=3.5, fig.height=3.5>>=
	plot(1:100, rnorm(100), ylab = "A random value")
	@

	Knitr integrates R tables into your document.

	<<some_table, results='asis'>>=
	library(xtable)
	xtable(data.frame(a = 1:3, b = 11:13, c = 21:23))
	@

	\end{document}

`knitr` files use the suffix `.Rnw` and contain a combination of regular LaTeX and chunks of R code. These chunks begin with `<<name_of_the_chunk, options>>=` and end in a line containing a single `@`. When you compile your document, `knitr` evaluates the code chunks and produces a `.tex` file which can be compiled using `pdflatex`. `knitr` will try to present the results of the R code as nicely as it can, but there are plenty of [options][knitr_options] to customize its behavior. For example we use the `fig.width` and `fig.height` options to control the size of the resulting plot in our second chunk. We use `results='asis'` for the table, because `xtable()` produces `LaTeX` code that we want to insert 'as it is'. Here is the [pdf produced by the above code][knitr_example]. It looks quite nice already.

## How to knit in Sublime Text 3

There are three packages for Sublime Text 3 that make knitting a walk in the
park:

1. [`SublimeKnitr`][sublime_knitr] provides syntax highlighting and some editing capabilities for `knitr` files.
2. Our very own [`LaTeXing`][latexing] handles `knitr` files just like regular `LaTeX` files. Simply hit `Ctrl+b` (or `Super+b` on a Mac) to build.
3. [`Enhanced-R`][enhanced_r] allows you to send code from your `knitr` document to `R`.

The easiest way to install these plugins is to get [Package Control][pc], bring up the command palette (`Strg+Shift+p` on Windows and Linux, `Super+Shift+p` on the Mac), select `Package Control: Install Package`, select the package you want, and hit enter. You can easily get things up and running in three minutes or less.

To enable `knitr` support in `LaTeXing` you only have to add a single option to your LaTeXing settings: (In the menu select Preferences/Package Settings/LaTeXing/Settings - User and insert the following line.)

	"knitr": true

Now, copy the sample code above, paste it into a new file, and save it as `something.Rnw` in a folder of your liking. Hit `Ctrl+b` (or `Super+b` on a Mac) to create the pdf.

While I am working on my `R` code I prefer not to build the whole document all the time. Instead I have an instance of `R` running and use `Ctrl+enter` to send the current line or selection to `R`. `Ctrl+Shift+Alt+r` (`Super+Shift+Alt+r` on a Mac) sends the current chunk instead. This capability is provided by `Enhanced-R`. It should work out of the box if you use the `R GUI` on Windows or Mac or run `R` inside `tmux` on Linux. `screen` is also supported on Linux.

## Summary and where to go next

knitr is a great way to keep your LaTeX and R code together. LaTeXing
has dead simple support for knitr and together with SublimeKnitr and
Enhanced-R it provides all the tools you need to use knitr in Sublime Text 3.

[knitr's website][knitr] is a good place to find out
more about knitr's features such as its caching and graphics
capabilities. It provides a number of
[demos][knitr_demos] that will get you started on the
basics.

A big thanks to **Severin** for writing up this tutorial!!

[knitr]: http://yihui.name/knitr/
[knitr_demos]: http://yihui.name/knitr/demos
[knitr_example]: files/knitr_example.pdf
[knitr_options]: http://yihui.name/knitr/options
[sublime_knitr]: https://github.com/andrewheiss/SublimeKnitr
[latexing]: http://www.latexing.com/
[enhanced_r]: https://github.com/randy3k/Enhanced-R
[pc]: https://sublime.wbond.net/installation
