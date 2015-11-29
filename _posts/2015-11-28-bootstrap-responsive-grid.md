---
layout: post
title: Bootstrap Responsive Grid Layout
tags: bootstrap, responsive
---

It might be a bit confusing for first time users of bootstrap but in order to utilize the grids for repsonsive design, you will need to use a multitude of the grid classes. For example:

    <div class="col-md-12 col-sm-6 col-xs-12">
		<p>This div will look different in different viewports</p>
    </div>

The previous div will take the whole line in laptops, half a line in tablets, and the whole line in mobile devices. Following the same 12 grid layout, you can easily resize elements of the page based on the viewports you are trying to target.