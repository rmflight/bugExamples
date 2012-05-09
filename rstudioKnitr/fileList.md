I would like to have the ability to turn off `markdownToHTML` `safe_link` option to off when using the RStudio `knitHTML` button, or know how to use the RStudio CSS, syntax highlight, and other goodness included when I call `knit` on my own files from the command line so that I can include internal links in my reports (very useful for TOC's).

The files listed below (and are in this directory) give examples of what I mean.

# Steps to create files

# mdExample_rstudioPreview.html

Open 'mdExample.md', and use the "preview buttion" in RStudio to generate html, save the html file. This file has no internal links in the HTML.

# mdExample_knit2html.html

```r
library(knitr)
knit2html("mdExample.md", "mdExample_knit2html.html")
```

Neither does this one, which I expect.

# mdExample_md2html.html

```r
library(markdown)
options(markdown.HTML.options=NULL)
markdownToHTML("mdExample.md", "mdExample_md2html.html")
```
This one has internal links, because I set the `markdown` options first.

If I do the `knitr` version again now, internal links will work.

`knit2html("mdExample.md", "mdExample_knit2html_2.html")`

But if I try using the RStudio preview again, it doesn't work (see "mdExample_rstudioPreview_2.html").


