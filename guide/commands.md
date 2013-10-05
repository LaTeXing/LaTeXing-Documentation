# Commands

These commands are available from the command palette. Some of these commands
in this section are also available via a key binding, therefore you have to
check the corresponding section in the key bindings for these commands.

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

## Check System

LaTeXing requires different command-line tools to support all functions. The
most important command-line tool (and mandatory for compilation) is "latexmk".
The "latexmk" tool is shipped with all big LaTeX distributions, such as
TeXlive, MacTeX, and MikTeX; for others it may be required to install it
manually.

LaTeXing offers a tool to check if all required tools (latexmk, perl,
texcount, kpswhich, mthelp for MikTeX, texdoc for TeXlive or MacTeX) are
available in your system; to run it, click on Tools > Packages > LaTeXing >
Check System. Some of these commands, like "texdoc", are not mandatory but are
still helpful during your daily work. Attached to the test, LaTeXing opens a
window with a list of all the required tools and the total status of your
system.

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

## Insert TeX Symbol

**Keybinding:** `§` (OS X) or <code>\`</code> (Windows, Linux)

LaTeXing helps you to fill TeX symbols, this are for example simple Greek
letters or more complex arrows or symbols. After hitting the trigger, a menu
will appear and you can choose the symbol out of that list. The behaviour is a
wee bit more complex and need some extra explanation, please check the
tutorial section.

## Lookup TeX Symbol

Opens the browser at [detexify.kirelabs.org][detexify], on this website you
can sketch a symbol and see the possible latex commands to generate it.

## Phrases Dictionary

Open any available phrase dictionary.

## Word to Phrases Dictionary

**Keybinding:** `cmd + l, cmd + u`

LaTeXing helps you to fill often used phrases in your report. With this
command you can add one ore more selctions to you defined phrases dictionary,
please check the tutorial section

## Synchronise Remote Data

If you changed any remote data like on Bibsonomy, Citeulike, Mendeley or
Zotero you can synchronise the data by using this command. There is a
different between rebuilding the cache and this command, this command will
just refetching updated items rather than fetching all available items.

## Update Bibliography File(s)

After you already synchronised your remote data, the content of a bibliography
could be different, with this command the cached data and the bibliography are
going to compared and if required the bibliography file filled with the
required informations.

## Rebuild Cache

One new feature of LaTeXing 0.8 is a cache function to improve the working
speed with big projects. With this command you can rebuild the cache on the
soft way which means that just the timestamps are going to be adjusted and you
are not cleaning the cache rather than just re-fetching all informations.

## Rebuild Cache (Hard)

This command is rebuilding the cache on a hard way, deleting all files and be
ready to build the cache new while working from scratch. Normally this
shouldn't be required because LaTeXing is also checking the cache every
startup for unavailable cached options to keep the cached data small. If you
have problems, please rebuild the cache anyway.

## Texcount

The word count of LaTeX files isn’t always an easy task but with LaTeXing this
is very easy. This feature uses the command line tool texcount and gives a
message after executing with the total words, the words in headers as well as
the word in captions.

![image](images/texcount.jpg)

## Toggle Preferences

**Keybinding:** `cmd + l, cmd + t`

Provides a list of the simple preference options of LaTeXing with the
possibility of toggle them. This command can access boolean options, to these
options which can be either true or false. With this command it is possible to
quick disable or enable the use of the forward search for the generated file
for example.

[detexify]: http://detexify.kirelabs.org/classify.html