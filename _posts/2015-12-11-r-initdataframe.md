---
layout: post
title: Initializing empty data frames
tags: R
---

Initializing empty data frames is very simple, just create a data frame with matrixes with the specified number of columns and rows. For example:  
    cat = data.frame(matrix(nrow=2, ncol=2))

The resulting data frame will look like this:  
      X1 X2
    1 NA NA
    2 NA NA