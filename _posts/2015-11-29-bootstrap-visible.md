---
layout: post
title: Bootstrap Responsive Utilities
tags: bootstrap, responsive
---

Following up on my previous post on Bootstrap is the visisble and hidden class. Visible and hidden are used to simply show and hide elements for different viewports. Use them in conjunction with the grid system in order to create highly responsive webpages. For example:

    <div class="col-md-12 col-sm-12 col-xs-12">
		<div class="col-md-4 col-sm-6 col-xs-12">Col 1</div>
		<div class="col-md-4 col-sm-6 col-xs-12">Col 2</div>
		<div class="col-md-4 col-sm-6 col-xs-12">Col 3</div>
		<div class="col-md-12 visible-md">Footer header</div>
		<div class="col-xs-12 hidden-md">Footer footer</div>
    </div>

Two elements are hidden and visible. The first visible div makes it so only those of the md viewport can see that element. The hidden div makes it so that the last element is hidden for the md viewport. 