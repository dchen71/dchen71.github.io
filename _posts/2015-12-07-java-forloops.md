---
layout: post
title: For loops in Java
tags: java
---

For loops can be setup in Java in two ways. The first way is to an initialization value and increment until the termination statement. For example:

    int endpoint = 5;
    for(int start = 0; start <= endpoint; start++){
    	System.out.println(start);
    }

The previous example will run 5 times and print the start value each time. The other way is to loop through each value in a array like the following:

    int[] numbers = {1,2,3};
    for(int number : numbers){
    	System.out.println(number);
    }

The previous loop will run through each element in the array and print out the int value.