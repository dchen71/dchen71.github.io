---
layout: post
title: Bag of Words in R
tags: python, defaultdict
---

defaultdict is part of the collections module in python and is used similarly to having called the setdefault method of regular dictionaries for every value. For example:

    #Regular dictionary
    cat = dict()
    cat.setdefault("dog", 5)
    
    #defaultdict
    from collections import defaultdict
    cat = defaultdict()
    cat["dog"] = 5

In either case, cat is assigned a key of dog and a value of 5. defaultdict does have the distinct advantage of not having to write dict.setdefault() all the time. They are both useful elements of data structures to aid with initializing values in the dictionary.