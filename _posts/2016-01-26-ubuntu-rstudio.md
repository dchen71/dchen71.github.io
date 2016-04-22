---
layout: post
title: Fixing issue with Rstudio not loading
tags: ubuntu, rstudio
---

Recently, I encountered an issue in which RStudio would not load on a fresh install of Ubuntu. It took me a while to find the direct fix but anyways the following should work in installing all the UTF-8 locale files that you may need to be able to run the program.

  sudo dpkg-reconfigure locales

The files should install if you don't already have them and RStudio may work for you.