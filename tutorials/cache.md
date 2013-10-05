# Cache Support of LaTeXing

One new feature of LaTeXing 0.8 is a cache function to improve the working
speed with big projects. Here is a short summary of the major informations:

## Types

Name              | Content
----------------- | ----------------------------
doc.cache         | Result of texdoc command
pkg.cache         | LaTeX packages and classes, biblograpy styles
tex.cache         | TeX files
bib.cache         | Biblograpy files
bibsonomy.cache   | Bibsonomy data
citeulike.cache   | CiteuLike data
mendedely.cache   | Mendeley data
zotero.cache      | Zotero data

## Workflow


For you as user there is no change while writing LaTeX files but under the
hood there are some changes. When you start Sublime Text, LaTeXing is fetching
the existing cache data, this may take a moment depending on your cache size.
The cache will be updated after every build but no more than every 5 minutes
to keep the performance of the whole system high with huge cache files.

## Commands

You can rebuild the cache informations, there are two different ways: a normal
rebuild and a hard rebuild. The hard rebuild will delete all cache files and
you can start from scratch. On the other hand the normal rebuild will just
adjust the timestamps and execute a normal rebuild after a cache time out.

On a rebuild, for example the doc.cache, LaTeXing will check the documentation
for every cached package again and if not available delete the item. For the
tex.cache LaTeXing will check the cached files and if a file is not available
any more this cache item will be also cleaned.
