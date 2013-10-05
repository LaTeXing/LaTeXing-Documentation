# Internal Options

LaTeXing offers some options which needs to be filled in the TeX files, these
options need to be inserted at the top of a file, before any other command,
with the following syntax: `% -*- key: value -*-`. The option key can be one
of the following values.

## root

This option is for the multi-document support to connect subfiles with a root
document. Please see the particular section for multi-document support for
more informations about the project support, see the tutorial section for an
example to build up a project.

## pdf

This option is just affecting the root document and defines the PDF file name.
Normally the PDF name is a normalised version of the file name of the root TeX
file but with this option you can freely customise the output PDF name.

## phrases

You have the chance to define a dictionary with often used phrases, the
content if this dictionary will be included in the normal autocompletion,
check the tutorial section for more details.

## program

You can change the program used for the typeset, the possible values are
xelatex and lualatex.

## prefix

Set a unique prefix for the current file, e.g. for creating labels

> You can also place any of this options in a Sublime Text project file, check
> the tutorial section.
