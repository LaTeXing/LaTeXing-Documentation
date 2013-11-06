# Sublime Settings

LaTeXing allows you adjust many settings, all this options are located in the
LaTeXing.sublime-settings file inside the package directory. Please copy the
file into your user directory and change the settings there. This will keep
your settings even if you update LaTeXing.

## username, license

Fill your license from LaTeXing.com, thanks for the support!!!

## log

Debug informations inside the python console, just for test purposes, this may
slow down the plugin.

## fallback\_encoding

Adjust this if you have problems with the encoding

## path

Adjust the path where executable programs are located. For example for
accessing curl on Linux for using the https connection with Zotero if the SSL
module is not available

## show\_log\_panel\_on

Open the log panel after every build for the items in the list, if no item in
the list match the log will automatically close.

## keep\_focus, -\_delay

Sublime Text retains focus after a successful typset of your PDF file.. If
false, the PDF viewer will gain focus. Some PDF Viewer do not provide an
option to open the PDF file in the background, in this cases LaTeXing will
switch back to Sublime Text after a short delay.

## executables

This can be used as a fallback setting, in general you should prefer setting
the required tools to your path but if you cannot solve it please adjust this
setting to define an absolute path. In some situation LaTeXing needs to know
where the Sublime Text binary (executable) file is located. If the keep focus
setting to not work be sure Sublime Text is available on your path or adjust
the path below.

## forward\_sync, reverse\_sync

LaTeXing offers a full support for SyncTeX

- forward\_sync: Support to jump from the TeX file to the corresponding
  position inside the PDF
- reverse\_sync: Support to jump back from the PDF file into the TeX file at
  the selected position

This requires additional settings for some PDF viewers, please check
docs.latexing.com for more information. This feature is just supported by:
Skim on OS X, SumatraPDF on Windows, and Evince or Okular on Linux

## pdf\_viewer\_osx, -\_windows, -\_linux, -\_order

Set your favourite PDF viewer for the different OS's, order in
pdf\_viewer\_order defines the priority. For example on OS X is Skim the first
choice but if this program is not available Preview will be used instead.

Supported viewer:

- OSX: Skim and Preview
- Windows: Sumatra PDF, Adobe Reader, Foxit Reader, PDF XChange Viewer
- Linux: Evince and Okular

> forward\_sync and reverse\_sync is just supported by Skim, Sumatra PDF,
> Evince and Okular

## phrases, -\_mode, -\_min\_count, -\_min\_length, -\_max\_length, -\_bounding\_words

With LaTeXing the auto completion is extended to use multi word phrases. This
words are often used phrases and LaTeXing helps to complete this phrases in no
time.

- phrases: enable the analyse of phrases
- phrases\_mode: phrases dictionary (0), current file (1), whole project (2)
- phrases\_min\_count: minimum count of phrases to be visible
- phrases\_min\_length: minimum length of the phrase
- phrases\_max\_length: maximum length of the phrase
- phrases\_bounding\_words: stop the phrase at these word

## partial\_build

If partial build is enabled mode, just the document that is currently being
edited is built. All the preambles of root document will be included as well,
so you are not losing any settings while a partial build.

This can be useful if you for example just would like to typeset one single
chapter of a whole project. Apart from the preambles, the bibliography will
also be included.

## open\_pdf\_on\_load

Once you are opening a supported LaTeX source file LaTeXing can open the
corresponding PDF file together with the current loaded file.

## typeset\_on\_save

Typeset the document on saving it

## type\_scrolling

Set the line you are working on automatically as vertical center of your
screen

## output\_directory

LaTeXing can use an output\_directory to seperate the generated files from the
source code. This directory can be relative to the root document or can be an
absolute path anywhere on your disk (be sure that the directory is writable).
In case you set an directory outside of your TEX file dictionary LaTeXing will
add the PDF name to the path.

## default\_tex\_extension, default\_bib\_extension

Define the default TEX and BIB file extension, this is used if no extension is
defined and one is required.

## tex\_pattern

Define the TeX pattern, the search pattern of the provided list for the fill
command of the input, include, subfile commands

## graphics\_pattern, currfile\_graphicspath

Define the graphics pattern, the search pattern of the provided list for the
fill command of "includegraphics".

The option "currfile\_graphicspath" enables the use of the package currfile
and a changed graphicspath in huge projects like this in you TeX file:
\graphicspath{\currfiledir}

## auto\_trigger\_fill

Auto trigger the fill command of TeX commands with the starting curly brake or
the comma between two items. For example typing a { after \cite will
automatically open the list with the available citations

## cite\_panel\_format

Customise the citation format of the quick panel for filling the cite command.
The available variables are {title}, {stitle}, {author}, {sauthor}, {year},
{journal}, {key} as well as {origin} which is the location of the item

## label\_format, label\_type

Customise the format of the label, the available keys are type, prefix, name;
the value for type is defined by label\_type below. Please note that a
normalised version of the file name will be used if no prefix is defined and
you are not in your root document.

## foldable\_environments

Define a list of environments which are available to fold without based on
indention, by default table, figure, equation environments can be fold.

## static\_cwl, dynamic\_cwl

LaTeXing offers full support of the open source plugin LaTeX-cwl which can be
found [here](https://github.com/Chris---/LaTeX-cwl).

In addition to the provided cwl files by the plugin you have the ability to
save your own files under “User/cwl” within the Sublime Text package
directory.

By default LaTeXing is loading the files defined in static\_cwl. If
dynamic\_cwl is enabled LaTeXing is checking for the used files and loading
the relevant files.

## build\_arguments

Provide additional build arguments for latexmk, e.g. -shell-escape

## symbols\_in\_category

Sort the symbols of the command "Insert TeX Symbols" in categories

## cache\_timeout

Defines the time interval (in hours) when LaTeXing will re-fetch the relevant
informations automatically at a startup of Sublime Text. You can also rebuild
the cache manually using the command from the command palette. If you would
not like to use the cache just disable this settings to 0.

The advantage of using the cache is mostly beneficial by using the online
services of big projects which word phrases completion. For each request
LaTeXing is looking firstly in the cache and just if the file is outdated
parse all information new.

## remote\_bibliography\_in\_category

Define if you would like to organise the remote bibliography items in a own
category instead of showing them together with all available local items

## bibname

Define the name of the bibliography file which should be used to save the
fetched items from a remote bibliography source

## update\_remote\_bibliography

If you are using items from a remote bibliography source LaTeXing can keep
track of the changes and update the local copy before a build.

## cite\_key\_blacklist

Skip this words while building the citation key of the bibliography items,
case insensitive.

## bibsonomy, -\_username, -\_apikey, -\_internal\_cite\_key, -\_cite_key_pattern

Just enable bibsonomy to activate the support. LaTeXing will get the other
necessary data automatically, please check docs.latexing.com for details.

You can also adjust the pattern to create a citation key if available, the
available keys here: {Author}, {author}, {Year}, {Title}, {title}

## bibsonomy, -\_username, -\_internal\_cite\_key, -\_cite_key_pattern

Just enable citeulike to activate the support. LaTeXing will ask you for all
necessary data automatically, please check docs.latexing.com for details.

You can also adjust the pattern to create a citation key if available, the
available keys here: {Author}, {author}, {Year}, {Title}, {title}

## mendeley, -\_oauth\_token, -\_oauth\_token\_secret, -\_internal\_cite\_key, -\_cite\_key\_pattern

Just enable mendley to activate the support. LaTeXing will get the other
necessary data automatically, please check docs.latexing.com for details.

You can also adjust the pattern to create a citation key if available, the
available keys here: {Author}, {author}, {year}, {Title}, {title}

## zotero, -\_user\_id, -\_user\_key, -\_cite\_key\_pattern

Just enable zotero to activate the support. LaTeXing will get the other
necessary data automatically, please check docs.latexing.com for details.

You can also adjust the pattern to create a citation key if available, the
available keys here: {Author}, {author}, {Year}, {Title}, {title}

## global\_bib\_file, -\_path

Here you can enable and define a global bibliography file which works like a
kind of local repository for your bibliography items. You can import easily
items from this file like the same way using the remote bibliography system.
This can be useful if you exported all your references in one big file (e.g.
from your local Mendeley application).

## online\_lookup

LaTeXing offers the support of running a command in the web browser with the
selected word as argument. For example it is possible to look up for a
definition or translation of a word very quick and easily.

## knitr, -\_command

Just enable the support, please be sure Rscript is available on your path or
set an absolute location for the Rscript executable

## tikz, -\_create\_pdf

Just enable the support and every *.tikz file will compile and build on her
own very fast. If tikz\_create\_pdf is enabled the created pdf is also copied
next to your source file to include it as figure.