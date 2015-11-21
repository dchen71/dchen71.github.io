---
layout: post
title: Aggregate in R
tags: r, functions
---

One handy function that took me forever to realize existed outside of R packages is aggregate. Aggregate works similarly to the group by and aggregate methods in SQL. Simply put, aggregate combines multiple values into a single cell. For example:

    data("ToothGrowth")
    aggregate(len ~ . , data=ToothGrowth, mean)

Aggregate returns the aggregated mean len value from the ToothGrowth dataset against supp and dose as can be seen in the following.

      supp dose   len
    1   OJ  0.5 13.23
    2   VC  0.5  7.98
    3   OJ  1.0 22.70
    4   VC  1.0 16.77
    5   OJ  2.0 26.06
    6   VC  2.0 26.14

Aggregate can be used for against a single variable such as finding the median of dosage length.

    aggregate(len ~ dose , data=ToothGrowth, median)

And the following results from calling aggregate:

      dose   len
    1  0.5  9.85
    2  1.0 19.25
    3  2.0 25.95