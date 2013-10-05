# Using glossaries with LaTeXing

The glossaries package can be used to create glossaries. It supports multiple glossaries, acronyms, and symbols. The setup is sometimes a bit difficult but here we are working throught it how to use it with LaTeXing.

Let's consider an example before we talk about the setup in detail.

	\documentclass{article}
	\usepackage[colorlinks]{hyperref}
	\usepackage[acronym]{glossaries}

	\makeglossaries

	\newglossaryentry{sample}{
		name={sample},
		description={a sample entry}
	}

	\newacronym[
		\glsshortpluralkey=cas,
		\glslongpluralkey=contrived acronyms]{aca}{aca}{a contrived acronym}

	\begin{document}

	A \gls{sample} entry and \gls{aca}. Second use: \gls{aca}.

	Plurals: \glspl{sample}. Reset acronym\glsreset{aca}.
	First use: \glspl{aca}. Second use: \glspl{aca}.

	\printglossaries

	\end{document}

Now we have to adjust the .latexmkrc file like following inside the root of our project.

	add_cus_dep('glo', 'gls', 0, 'makeglo2gls');
	add_cus_dep('acn', 'acr', 0, 'makeglo2gls');
	sub makeglo2gls {
	  my ($base_name, $path) = fileparse( $_[0] );
		pushd($path);
		system("makeglossaries $base_name");
		popd;
	}

The file can be places also at the default locations for latexmk to find it. After saving the file at the right place everything should work like before. **Be sure makeglossaries is available on your path.**