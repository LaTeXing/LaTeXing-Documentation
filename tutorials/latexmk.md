# Extend latexmk with LaTeXing

[Latexmk][latexmk] is a perl script for running LaTeX the correct number of times to resolve cross references, etc; it also runs auxiliary programs. Sometimes it needs some extra settings to workout particular problems. The creation of an `latexmkrc` is required to add extra compile steps.

The file can be places in the root of your project or at the default locations for latexmk to activate it system wide. Please check the package [documentation][latexmk] for more details. After saving the file at the right place everything should work like before.


## Glossaries

The [glossaries][glossaries] package can be used to create glossaries. It supports multiple glossaries, acronyms, and symbols. The setup is sometimes a bit difficult but here we are working throught it how to use it with LaTeXing without loosing any comfort.

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

If you run the build command like usual you will gain into a error message like this.

    [Compile ~/Desktop/Glossaries/Document.tex]

    W: /Users/chris/Desktop/Glossaries/Document.tex:0 No file Document.gls.
    W: /Users/chris/Desktop/Glossaries/Document.tex:0 No file Document.acr.

    0 errors, 2 warnings, 0 badboxes

    [Finished in 1.46s]

This is based on the fact that the glossaries command was never executed. To register the command with latexmk we just have to adjust the .latexmkrc file like following inside the root of our project.

    add_cus_dep('glo', 'gls', 0, 'makeglo2gls');
    add_cus_dep('acn', 'acr', 0, 'makeglo2gls');
    sub makeglo2gls {
      my ($base_name, $path) = fileparse( $_[0] );
      pushd($path);
      system("makeglossaries $base_name");
      popd;
    }

**Be sure makeglossaries is available on your path.**

## Normncl

The [normcl][nomencl] produces lists of symbols using the capabilities of the MakeIndex program. To register the command with latexmk we just have to adjust the .latexmkrc file like following.

    add_cus_dep('nlo', 'nls', 0, 'makenlo2nls');
    sub makenlo2nls {
    my ($base_name, $path) = fileparse( $_[0] );
    pushd($path);
    system( "makeindex -s nomencl.ist -o \"$base_name.nls\" \"$base_name.nlo\"" );
    popd;
    }

**Be sure makeindex is available on your path.**

[latexmk]: http://www.ctan.org/pkg/latexmk
[glossaries]: http://www.ctan.org/pkg/glossaries
[nomencl]: http://www.ctan.org/pkg/nomencl