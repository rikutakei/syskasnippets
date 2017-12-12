---
title: aRson threats and some best practices
author: Murray Cadzow
date: '2017-12-12'
slug: arson-threats-and-some-best-practices
categories: [R, Best practices]
tags: [R, Jenny Bryan]
description: ''

---

Recently on twitter - the source of most of these posts - Jenny Bryan (@JennyBryan) posted a link to her slides from her talk she gave in Auckland (http://bit.ly/jenny-nz). It inpsired threats of arson for people that use

```
setwd("/absolute/path/to/file")
```

(this was because it reduces portability and outside of you using it the chances of someone having the exact directory setup is basically 0%)

and 

```
rm(list = ls())
```

(because it interferes with peoples sessions and doesn't sort out other session issues such as packages already loaded)

at the start of their scripts. There is now a post that is well worth reading about why not doing this is a good idea https://www.tidyverse.org/articles/2017/12/workflow-vs-script/

It raises some really good points building on the overall theme of working within a project setup and in such a way that the project is a self contained entity that can essnetially be transferred anywhere and is not reliant on an external directory setup.

Perhaps someone may take the chance to create a package/rstudio addin called aRson that checks for those commands at the top of scripts...seems almost too good an opportunity to miss!