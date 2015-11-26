---
layout: post
title: Reading text files in python
tags: python
---

Just a quick gist on how to open and read text files without the new line characters.

    f = open("readme.txt")
    text = []
    for line in f:
		text.append(line.rstrip())
	f.close()