---
layout: post
title: Changing system locale in R
tags: R
---

Reading characters in R is pretty simple. To do so, read the data file with encoding in UTF-8. Then set the sys locale to the locale thatyou need. For example, to set the locale to Japanese, do the following:

    Sys.setlocale(category="LC_ALL", locale = "japanese")

And to change back to US English:

    Sys.setlocale(category="LC_ALL", locale = "English_United States.1252")