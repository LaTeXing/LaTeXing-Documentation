# Key Bindings

LaTeXing offers a wide range of key bindings to make your work more efficient
and comfortable; these commands are listed and explained following:

## Fill Command

**Keybinding:** `cmd + l, cmd + l`

The basic idea of this command is to help you out with inserting values in
commands. The support of the commands is wide and the action depends on the
selected command. For example it is possible to fill the argument of an
\includegraphics command with the path to a figure just by selecting the item
out of a list or the path of a subfile for the
\include command. The supported commands are:

**\usepackage**

Provides a list of the installed packages, it is possible to search and select
an individual package. The list just contains the local available packages of
your LaTeX distribution and will be refreshed every 48 hours, so if you would
like to deleted the cached file, please rebuild the cache

**\documentclass**

Provides a list of the installed document classes, it is possible to search
and select an individual class. The list just contains the local available
classes of your LaTeX distribution and will be refreshed every 48 hours, so if
you would like to deleted the cached file, please rebuild the cache.

**\include, \input, \subfile**

Provides a list of TeX files related to the current TeX file, the filter for
the available files can be adjusted in the settings, the default configuration
includes *.tex and *.ltx files. The command subfile is just available with the
popular subfiles package.

**\includegraphics**

Provides a list of image files related to the current TeX file, the filter for
the available files can be adjusted in the settings, the default configuration
includes *.jpeg, *.jpg, *.png, *.eps, and *.pdf files. To support the currfile
packages LaTeXing offers an option that the path of the image file can be
either relative to the root file within a project or relative to the current
working directory.

**\caption**

This command is only available within a table and figure environment, it
normalise the caption and adds a label to the next line. For example executing
it within caption{Text Caption Figure 1} inside a figure environment will
normalise the caption and insert the following to the next line:
label{fig:text\_caption\_figure\_1}. The used fig prefix is for a figure, for
a table tbl will be used, this makes it comfortable to create quick readable
labels for references.

**\part, \chapter, \section, \paragraph**

Similar to captions it is possible to create normalised labels of the selected
part, chapter, section, or paragraph for your citations. The used prefix
varies for the selected command, for example a part uses prt, a chapter cha,
or a section sec.

**\bibliography**

Provides a list of bibliography files related to the current TeX file, the
filter for the available files can be adjusted in the settings, the default
configuration includes *.bib files.

**\cite, \nocite**

Provides a list of the available citations, LaTeXing searched trough all the
included bibliography files and lists the related items. Thanks to the project
support, multi-documents are fully supported, see the related section in the
documentation for more informations. Additional to the local citations it is
very easy to import citations from the online reference service Bibsonomy.org,
please see the related section within the documentations for further
informations how to configure and use it properly. LaTeXing makes it possible
to use this function also within mutations of the actual \cite command like
\citeyear or
\citet.

**\ref, \cref**

Provides a list of the available references, LaTeXing also supports multi-
documents for cross references and list labels from included files as well as
the current file. The cleveref package is fully supported and therefore also
possible to use this function for commands like \cref, \namecref, or
\crefrange

**\ac**

Provides a list of the available abbreviations, this is just available with
the acronym package. All the acronym commands are supported please check the
package documentation for more informations and a complete list of commands
regarding this section.

**\label**

This function is not really a fill command but it could be counted as this
since there are no possible values for a label expect the name. By pressing
the key combination LaTeXing offers an input box and you can rename the
current label thought your whole project.

## Fill Anywhere Command

**Keybinding:** `shift + cmd + l, shift + cmd + l`

The fill anywhere command is providing similar functions like the fill command
with the addition that a drop down menu will let you choose what you would
like to do at the current selection. For captions and headings is this
function useless and so not available but for other commands is this might be
useful. For example it could be required to fill a image path somewhere else
then just the normal includegraphics command. The fill anywhere command is
available for \include, \input, \subfile. \includegraphics, \ref, \cite, and
\ac commands and there mutations like usual.

## Open Command

**Keybinding:** `cmd + l, cmd + k`

This command can open or follow a couple of commands, for example it is
possible to open a subfile, open a citation for fast editing, or follow a ref
cross reference to the corresponding label. The supported commands are:

**\documentclass**

Provides a list of the local documentations for the selected class, especially
during the learning process of using a new class is this feature very handy
and can save time to find the individual class documentation. The commando
line tool “texdoc” or “mthelp” is used and therefore required, the provided
list also offers a search on ctan.org and google.com to find an unavailable
class documentation online.

**\usepackage**

Provides a list of the local documentations for the selected package,
especially during the learning process of using a new package is this feature
very handy and can save time to find the individual package documentation. The
commando line tool “texdoc” or “mthelp” is used and therefore required, the
provided list also offers a search on ctan.org and google.com to find an
unavailable package documentation online.

**\include, \input, \subfile**

Just opens the used included LaTeX or bibliography file, very useful for big
projects and makes every action outside of Sublime Text unnecessary.

**\cite, \nocite**

Follows the selected citation by locating the item and open the bibliography
file if available. The supported commands are the same like for the fill
command of \cite commands, so check the correlated section for more
informations.

**\ref, \cref**

Follows the selected cross reference by location the item and open the LaTeX
file if available. The supported commands are the same like for the fill
command of \ref commands, so check the correlated section for more
informations.

**\ac**

Follows the selected abbreviation by location the abbreviation and open the
LaTeX file if available. The supported commands are the same like for the fill
command of \ac commands, so check the correlated section for more
informations.

**\label**

Follows the use of the current label throughout the whole project. You can
select a item from the list of just check the used locations and return to the
origin by pressing escape.

## Open Anywhere Command

**Keybinding:** `shift + cmd + l, shift + cmd + k`

The open anywhere command is providing similar functions like the open command
with the addition that you can try to open a file from the current selection.
This is very useful if you use user defined commands and you would like to
open the file which is defined as argument.

## Open PDF

**Keybinding:** `cmd + l, cmd + o`

LaTeXing makes is very easy to handle your work without leaving the text
editor, with this command it is possible to open the generated PDF file if
available. The option keep\_focus in the settings determines if the PDF viewer
will gain focus or Sublime Text will stay in the foreground.

## Jump to PDF

**Keybinding:** `cmd + l, cmd + j`

The function of this command is similar to the “Open PDF” command with the
small difference that the PDF viewer will always be focused after open the
file unrelated to the keep\_focus setting and jump to the correlated position
in the PDF file.

## Import Citation(s)

**Keybinding:** `cmd + l, cmd + r`

LaTeXing offers a wide support for the online reference systems
[Bibsonomy][bibsonomy], [Citeulike][citeulike], [Mendeley][mendeley], and
[Zotero][zotero]. It is possible to import a single post, multiple post by
tags, all available post, or even import post by searching for missing
citations in your TeX file. The import command is available for TeX files as
well as for bibliography files.

Apart from using Bibsonomy.org you can also configure a global bibliography
files which will be used for further as reference. This is very handy if you
use a global library exported by e.g. Mendeley.

## Toggle Preferences

**Keybinding:** `cmd + l, cmd + t`

Provides a list of the simple preference options of LaTeXing with the
possibility of toggle them. This command can access boolean options, to these
options which can be either true or false. With this command it is possible to
quick disable or enable the use of the forward search for the generated file
for example.

## Online Lookup

**Keybinding:** `cmd + l, cmd + d`

The online lookup function is very useful for the daily work and fully
customable from the settings and so adjustable for your own preferences. For
example it is possible to check for a translation, a definition, or a
thesaurus of a selected word or a custom phrase. If the cursor is located in
the middle of a word, LaTeXing will find the boundary and offers a list of
search options for the selected word or ask for a custom phrase. If the cursor
is already located at a word boundary or within spaces LaTeXing will ask for
for a phrase straight away.

## Insert TeX Symbol

**Keybinding:** `§` (OS X) or <code>\`</code> (Windows, Linux)

LaTeXing helps you to fill TeX symbols, this are for example simple Greek
letters or more complex arrows or symbols. After hitting the trigger, a menu
will appear and you can choose the symbol out of that list. The behaviour is a
wee bit more complex and need some extra explanation, please check the
tutorial section.

## Word to Phrases Dictionary

**Keybinding:** `cmd + l, cmd + u`

LaTeXing helps you to fill often used phrases in your report. With this
command you can add one ore more selctions to you defined phrases dictionary,
please check the tutorial section

## LaTeX Command

**Keybinding:** `cmd + l, cmd + c`

Create a new command with the currently selected word are command name.

## LaTeX Environment

**Keybinding:** `cmd + l, cmd + e`

Create a new environment with the currently selected word are environment
name.

**Keybinding:** `cmd + l, cmd + n`

Create a new environment with the curser at the environment name and after
pretting tab once in the middle of the environment.

## Build Options

**Keybinding:** `cmd + l, cmd + b`

Shows an overlay with the prefix Build: which will display all available build
commands for the selected mode.

## Clean Build

**Keybinding:** `shift + cmd + b`

Cleans the temporary files for the current project.

## Show Commands

**Keybinding:** `cmd + l, cmd + p`

Shows an overlay with the prefix LaTeXing: which will display all available
LaTeXing commands for the selected mode.

## Show Snippets

**Keybinding:** `cmd + l, cmd + s`

Shows an overlay with the prefix Snippet: which will display all available
snippets for the selected mode.

## Text Decoration

**Keybinding:** `cmd + l, cmd + w, b`

Wrap the selected text in the command \textbf and so bold the text.

**Keybinding:** `cmd + l, cmd + w, e`

Wrap the selected text in the command \emph and so emphasise the text.

**Keybinding:** `cmd + l, cmd + w, u`

Wrap the selected text in the command \underline and so underlines the text.

## LaTeX Commands

**Keybinding:** `shift + enter`

This will insert a double backslash and a new line at the current location,
useful within a table environment.

**Keybinding:** `shift + enter`

This command is available within a list environment and insert a new line and
prepares a new list item (also available within the beamer class).

## BibTeX Commands

**Keybinding:** `@`

Shows an overlay with the prefix Snippet: Bibtex which will display all
available snippets inside a BibTeX.

**Keybinding:** `cmd + l, cmd + r`

See [here]({{env::request}}#import-citation-s).

## Special Characters

**Keybinding:** `tab`

Pressing tab right behind the following symbols with escape the symbol to work
with LaTeX like following:

    %, #, &, {, }, _   will change to   \%, \#, \&, \{, \}, \_

## Other Useful Stuff

**Keybinding:** `'`

This will auto pair single quotes.

**Keybinding:** `"`

This will auto pair double quotes.

**Keybinding:** `$`

This will auto pair in-line equations.

**Keybinding:** `(`

This will auto pair parentheses.

**Keybinding:** `{`

This will auto pair curly brackets.

**Keybinding:** `[`

This will auto pair square brackets.

**Keybinding:** `<`

This will auto pair angle brackets.

[bibsonomy]: http://www.bibsonomy.org
[citeulike]: http://www.citeulike.org
[mendeley]: http://www.mendeley.com
[zotero]: http://www.zotero.org
