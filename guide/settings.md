## Username and License Code

	/*
	 * Fill your license from LaTeXing.com, thanks for the support!!!
	 */

	"username": "",
	"license": "",

## Log

	/*
	 * Debug informations inside the python console, just for test purposes,
	 * this may slow down the plugin.
	 */

	"log": false,

## Quick Build Settings

	/*
	 * By default LaTeXing will use latexmk to build the pdf file, in some
	 * cases it is more convenient to use just a single pdflatex for example
	 * to refresh a huge file but don't care about missing cross references.
	 *
	 * You can also adjust the default build settings, be careful with this
	 * setting, it could break everything. To adjust this further you also
	 * need to change the sublime-build to provide further commands than the
	 * defaults.
	 */

	"quick_build": [
		{
			"name": "Default Build: latexmk",
			"primary": true,
			"cmds": ["pdflatex"]
		},
		{
			"name": "Quick Build 1: pdflatex + bibtex + pdflatex (2x)",
			"cmds": ["pdflatex", "bibtex", "pdflatex", "pdflatex"]
		},
		{
			"name": "Quick Build 2: pdflatex + biber + pdflatex (2x)",
			"cmds": ["pdflatex", "biber", "pdflatex", "pdflatex"]
		}
	],

## Fallback Encoding

	/*
	 * Adjust this if you have problems with the encoding
	 */

	"fallback_encoding": "utf_8",

## Path

	/*
	 * Adjust the path where executable programs are located. For example for
	 * accessing curl on Linux for using the https connection with Zotero if the
	 * SSL module is not available
	 */

	"path": [],

## Log Panel

	/*
	 * Open the log panel after every build for the items in the list, if no
	 * item in the list match the log will automatically close.
	 */

	"show_log_panel_on": ["errors", "warnings", "badboxes", "infos"],

## Keep Focus

	/*
	 * Sublime Text retains focus after a successful typset of your PDF file..
	 * If false, the PDF viewer will gain focus. Some PDF Viewer do not provide
	 * an option to open the PDF file in the background, in this cases LaTeXing
	 * will switch back to Sublime Text after a short delay.
	 */

	"keep_focus": true,
	"keep_focus_delay": 0.2,

## Executables

	/*
	 * This can be used as a fallback setting, in general you should prefer
	 * setting the required tools to your path but if you cannot solve it please
	 * adjust this setting to define an absolute path. In some situation
	 * LaTeXing needs to know where the Sublime Text binary (executable) file is
	 * located. If the keep focus setting to not work be sure Sublime Text is
	 * available on your path or adjust the path below.
	 */

	"executables": {
		// Required
		"perl": ["perl"],
		"latexmk": ["latexmk"],
		"pdflatex": ["pdflatex"],
		"xelatex": ["xelatex"],
		"lualatex": ["lualatex"],
		"sublime": ["subl", "sublime_text", "sublime_text.exe"],
		// Optional
		"kpsewhich": ["kpsewhich"],
		"mthelp": ["mthelp"],
		"texcount": ["texcount"],
		"texdoc": ["texdoc"],
		"rscript": ["Rscript"]
	},

## SyncTeX support

	/*
	 * LaTeXing offers a full support for SyncTeX
	 * forward_sync: Support to jump from the TeX file to the corresponding position inside the PDF
	 * reverse_sync: Support to jump back from the PDF file into the TeX file at the selected position
	 *
	 * This requires additional settings for some PDF viewers, please check
	 * docs.latexing.com for more information. This feature is just supported
	 * by: Skim on OS X, SumatraPDF on Windows, and Evince or Okular on Linux
	 */

	"forward_sync": true,
	"reverse_sync": true,

## PDF Viewer

	/*
	 * Set your favourite PDF viewer for the different OS's, order in
	 * pdf_viewer_order defines the priority. For example on OS X is Skim the
	 * first choice but if this program is not available Preview will be used
	 * instead.
	 *
	 * Supported viewer:
	 *   OSX: Skim and Preview
	 *   Windows: Sumatra PDF, Adobe Reader, Foxit Reader, PDF XChange Viewer
	 *   Linux: Evince and Okular
	 *
	 * forward_sync and reverse_sync is just supported by Skim, Sumatra PDF,
	 * Evince and Okular
	 */

	"pdf_viewer_osx": {
		"skim": [
			"/Applications/Skim.app"
		],
		"preview": [
			"/Applications/Preview.app"
		]
	},

	"pdf_viewer_windows": {
		"adobe_reader": [
		 "C:\\Program Files\\Adobe\\Reader 11.0\\Reader\\AcroRd32.exe",
		 "C:\\Program Files (x86)\\Adobe\\Reader 11.0\\Reader\\AcroRd32.exe"
		],
		"foxit_reader": [
			"C:\\Program Files\\Foxit Software\\Foxit Reader\\Foxit Reader.exe",
			"C:\\Program Files (x86)\\Foxit Software\\Foxit Reader\\Foxit Reader.exe"
		],
		"pdf_xchange_viewer": [
			"C:\\Program Files\\Tracker Software\\PDF Viewer\\PDFXCview.exe",
			"C:\\Program Files (x86)\\Tracker Software\\PDF Viewer\\PDFXCview.exe"
		],
		"sumatra_pdf": [
			"C:\\Program Files\\SumatraPDF\\SumatraPDF.exe",
			"C:\\Program Files (x86)\\SumatraPDF\\SumatraPDF.exe"
		]
	},

	"pdf_viewer_linux": {
		"evince": [
			"/usr/bin/evince"
		],
		"okular": [
			"/usr/bin/okular"
		]
	},

	"pdf_viewer_order" : [
		// OSX
		"skim",
		"preview",
		// Windows
		"sumatra_pdf",
		"adobe_reader",
		"foxit_reader",
		"pdf_xchange_viewer",
		// Linux
		"evince",
		"okular"
	],

## Phrases

	/*
	 * With LaTeXing the auto completion is extended to use multi word phrases.
	 * This words are often used phrases and LaTeXing helps to complete this
	 * phrases in no time.
	 *
	 * phrases: enable the analyse of phrases
	 * phrases_mode: phrases dictionary (0), current file (1), whole project (2)
	 * phrases_min_count: minimum count of phrases to be visible
	 * phrases_min_length: minimum length of the phrase
	 * phrases_max_length: maximum length of the phrase
	 * phrases_bounding_words: stop the phrase at these word
	 */

	"phrases": false,
	"phrases_mode": 0,
	"phrases_min_count": 2,
	"phrases_min_length": 3,
	"phrases_max_length": 5,
	"phrases_bounding_words": [],

## Partial Build

	/*
	 * If partial build is enabled mode, just the document that is currently
	 * being edited is built. All the preambles of root document will be
	 * included as well, so you are not losing any settings while a partial
	 * build.
	 *
	 * This can be useful if you for example just would like to typeset one
	 * single chapter of a whole project. Apart from the preambles, the
	 * bibliography will also be included.
	 */

	"partial_build": false,

## Open PDF on Load

	/*
	 * Once you are opening a supported LaTeX source file LaTeXing can open
	 * the corresponding PDF file together with the current loaded file.
	 */

	"open_pdf_on_load": true,

## Typeset on Save

	/*
	 * Typeset the document on saving it
	 */

	"typeset_on_save": false,

## Type Scrolling

	/*
	 * Set the line you are working on automatically as vertical center of
	 * your screen
	 */

	"type_scrolling": false,

## Output Directory

	/*
	 * LaTeXing can use an output directory to separate the generated files
	 * from the source code.
	 *
	 * output_directory: enables the use of an output directory
	 * output_directory_mode: use a relative directory named "Output" next to
	 * your source code (0) or use a temporary dictionary (1).
	 *
	 * Just can clean up the temporary dictionary by calling the "Clean
	 * Temporary Output Dictionary" command.
	 */

	"output_directory": false,
	"output_directory_mode": 0,

## Default Extensions

	/*
	 * Define the default TEX and BIB file extension, this is used if no
	 * extension is defined and one is required.
	 */

	"default_tex_extension": ".tex",
	"default_bib_extension": ".bib",

## TeX Pattern

	/*
	 * Define the TeX pattern, the search pattern of the provided list for the
	 * fill command of the input, include, subfile commands
	 */

	"tex_pattern": ["*.tex", "*.ltx", "*.tikz"],


## Graphics Pattern

	/*
	 * Define the graphics pattern, the search pattern of the provided list
	 * for the fill command of "includegraphics".
	 *
	 * The option "currfile_graphicspath" enables the use of the package
	 * currfile and a changed graphicspath in huge projects like this in you
	 * TeX file: \graphicspath{\currfiledir}
	 */

	"graphics_pattern": ["*.jpeg", "*.jpg", "*.png", "*.eps", "*.pdf"],
	"currfile_graphicspath": false,

## Auto Fill

	/*
	 * Auto trigger the fill command of TeX commands with the starting curly
	 * brake or the comma between two items. For example typing a { after
	 * \cite will automatically open the list with the available citations
	 */

	 "auto_trigger_fill": true,

## Citation Format

	/*
	 * Customise the citation format of the quick panel for filling the cite
	 * command. The available variables are {title}, {stitle}, {author},
	 * {sauthor}, {year}, {journal}, {key} as well as {origin} which is the
	 * location of the item
	 */

	"cite_panel_format": ["#{key}: {title}", "{type} ({origin}) by {author}"],

## Label Format

	/*
	 * Customise the format of the label, the available keys are type, prefix,
	 * name; the value for type is defined by label_type below. Please note
	 * that a normalised version of the file name will be used if no prefix is
	 * defined and you are not in your root document.
	 */

	"label_format": "{type}:{prefix}:{name}",
	"label_type": {
		"table": "tbl",
		"figure": "fig",
		"part": "prt",
		"chapter": "cha",
		"section": "sec",
		"subsection": "ssec",
		"subsubsection": "sssec",
		"paragraph": "par",
		"subparagraph": "spar"
	},

## Environment Folding

	/*
	 * Define a list of environments which are available to fold without based
	 * on indention, by default table, figure, equation environments can be
	 * fold.
	 */

	"foldable_environments": ["table", "figure", "equation"],

## Complete LaTeX Commands

	/*
	 * LaTeXing offers full support of the open source plugin LaTeX-cwl which
	 * can be found here (https://github.com/LaTeXing/LaTeX-cwl).
	 *
	 * In addition to the provided cwl files by the plugin you have the
	 * ability to save your own files under “User/cwl” within the Sublime Text
	 * package directory.
	 *
	 * By default LaTeXing is loading the files defined in static_cwl. If
	 * dynamic_cwl is enabled LaTeXing is checking for the used files and
	 * loading the relevant files.
	 */

	"static_cwl": ["tex.cwl", "latex-209.cwl", "latex-dev.cwl", "latex-document.cwl", "latex-l2tabu.cwl", "latex-mathsymbols.cwl"],
	"dynamic_cwl": true,

## Additional Build Arguments

	/*
	 * Provide additional build arguments for latexmk, e.g. -shell-escape
	 */

	"build_arguments": [],

## Symbols

	/*
	 * Sort the symbols of the command "Insert TeX Symbols" in categories
	 */

	"symbols_in_category": true,

## Cache

	/*
	 * Defines the time interval (in hours) when LaTeXing will re-fetch the
	 * relevant informations automatically at a startup of Sublime Text. You
	 * can also rebuild the cache manually using the command from the command
	 * palette. If you would not like to use the cache just disable this
	 * settings to 0.
	 *
	 * The advantage of using the cache is mostly beneficial by using the
	 * online services of big projects which word phrases completion. For each
	 * request LaTeXing is looking firstly in the cache and just if the file
	 * is outdated parse all information new.
	 */

	"cache": {
		"pkg": 168,
		"doc": 168,
		"tex": 24,
		"bib": 24,
		"bibsonomy": 48,
		"citeulike": 48,
		"mendeley": 48,
		"zotero": 48
	},

## Remote Bibliography Items

	/*
	 * Define if you would like to organise the remote bibliography items in a
	 * own category instead of showing them together with all available local
	 * items
	 */

	"remote_bibliography_in_category": false,

## Bibliography file name

	/*
	 * Define the name of the bibliography file which should be used to save
	 * the fetched items from a remote bibliography source
	 */

	"bibname": "Remote.bib",

## Automatic update remote bibliography

	/*
	 * If you are using items from a remote bibliography source LaTeXing can
	 * keep track of the changes and update the local copy before a build.
	 */

	"update_remote_bibliography": true,

## Skip words while building citation key

	/*
	 * Skip this words while building the citation key of the bibliography
	 * items, case insensitive.
	 */

	"cite_key_blacklist": ["the", "a", "an", "der", "die", "das"],

## Bibsonomy

	/*
	 * Just enable bibsonomy to activate the support. LaTeXing will get the
	 * other necessary data automatically, please check docs.latexing.com for
	 * details.
	 *
	 * You can also adjust the pattern to create a citation key if available,
	 * the available keys here: {Author}, {author}, {Year}, {Title}, {title}
	 */

	"bibsonomy": false,
	"bibsonomy_username": "",
	"bibsonomy_apikey": "",
	"bibsonomy_internal_cite_key": false,
	"bibsonomy_cite_key_pattern": "{Author}{Year}{Title}",

## Citeulike

	/*
	 * Just enable citeulike to activate the support. LaTeXing will ask you
	 * for all necessary data automatically, please check docs.latexing.com
	 * for details.
	 *
	 * You can also adjust the pattern to create a citation key if available,
	 * the available keys here: {Author}, {author}, {Year}, {Title}, {title}
	 */

	"citeulike": false,
	"citeulike_username": "",
	"citeulike_internal_cite_key": false,
	"citeulike_cite_key_pattern": "{Author}{Year}{Title}",

## Mendeley

	/*
	 * Just enable mendley to activate the support. LaTeXing will get the
	 * other necessary data automatically, please check docs.latexing.com for
	 * details.
	 *
	 * You can also adjust the pattern to create a citation key if available,
	 * the available keys here: {Author}, {author}, {Year}, {Title}, {title}
	 */

	"mendeley": false,
	"mendeley_oauth_token": "",
	"mendeley_oauth_token_secret": "",
	"mendeley_internal_cite_key": false,
	"mendeley_cite_key_pattern": "{Author}{Year}{Title}",

## Zotero

	/*
	 * Just enable zotero to activate the support. LaTeXing will get the other
	 * necessary data automatically, please check docs.latexing.com for
	 * details.
	 *
	 * You can also adjust the pattern to create a citation key, the available
	 * keys here: {Author}, {author}, {Year}, {Title}, {title}
	 */

	"zotero": false,
	"zotero_user_id": "",
	"zotero_user_key": "",
	"zotero_cite_key_pattern": "{Author}{Year}{Title}",

## Global Bibliography File

	/*
	 * Here you can enable and define a global bibliography file which works
	 * like a kind of local repository for your bibliography items. You can
	 * import easily items from this file like the same way using the remote
	 * bibliography system. This can be useful if you exported all your
	 * references in one big file (e.g. from your local Mendeley application).
	 */

	"global_bib_file": false,
	"global_bib_file_path": "",

## Online Lookup

	/*
	 * LaTeXing offers the support of running a command in the web browser
	 * with the selected word as argument. For example it is possible to look
	 * up for a definition or translation of a word very quick and easily.
	 */

	"online_lookup": [
		{
			"title": "Dict.cc",
			"url": "http://www.dict.cc/?s={query}"
		},
		{
			"title": "Dict.leo.org",
			"url": "http://dict.leo.org/ende/#/search={query}"
		},
		{
			"title": "Dictionary.com",
			"url": "http://dictionary.reference.com/browse/{query}"
		},
		{
			"title": "Linguee.com EN-DE",
			"url": "http://www.linguee.com/english-german/search?query={query}"
		},
		{
			"title": "Linguee.de DE-EN",
			"url": "http://www.linguee.de/deutsch-englisch/search?query={query}"
		},
		{
			"title": "Pons.eu",
			"url": "http://en.pons.eu/dict/search/results/?q={query}&l=deen"
		},
		{
			"title": "Thesaurus.com",
			"url": "http://thesaurus.com/browse/{query}"
		}
	],

## knitr support

	/*
	 * Just enable the support, please be sure Rscript is available on your
	 * path or set an absolute location for the Rscript executable
	 */

	"knitr": false,
	"knitr_command": "Rscript -e \"library(knitr); knit('{file}')\"",

## TikZ support

	/*
	 * Just enable the support and every *.tikz file will compile and build on
	 * her own very fast. If tikz_create_pdf is enabled the created pdf is
	 * also copied next to your source file to include it as figure.
	 */

	"tikz": false,
	"tikz_create_pdf": false