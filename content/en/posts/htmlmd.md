+++
title = "HTML to MD"
description = "HTML to Mardown Converter in Python"
tags = [
    "code",
    "python",
    "utility",
    "process"
]
featured_image = "/images/htmlmd.jpg"
date = "2020-08-12"
categories = [
    "python",
    "code",
    "utility",
    "process"
]
menu = "main"
+++


Quick idea

## Make an HTML to Markdown converter.
- make an html page with all elements
- python convert html to md equal element-code
- save as .md

```
import re

txt = "<h1>Headline H1</h1>"
x = re.search("^<h1>.*</h1>$", txt)
```
