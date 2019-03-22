---
layout: post
title:      "Using .sort_by"
date:       2019-03-22 14:16:46 -0400
permalink:  using_sort_by
---


.sort_by is a straightforward, but highly dynamic Ruby enumerator that shines at quickly organizing collections based on an attribute. As an alternative to Ruby's .sort, .sort_by provides an even easier implementation when sorting by a single attribute or parameter. Although it can be tricky to see the differences between these two methods at first, both achieve sorting in slightly different ways. Let's take a brief look at the differences between .sort and .sort_by.


**The .sort Method**

.sort relies on the comparison operator <=> to compare two elements in a collection.  If the second element is less than the preceding element, it will be rearranged into the proper order. "Less than", in this case, means the element that comes first alphabetically or numerically. If the second element is greater it will return -1, if the second element is less it will return +1, and if the elements are equal it will return 0. Ruby uses these return values to properly organize the collection from lowest to highest. 

The .sort method works by accepting two parameters, which represent the elements being compared - one parameter for the initial element and the other parameter for the element to compare to. If no parameters are given, .sort implicity evokes the comparison operator to organize the collection from lowest to highest. This method is excellent for simple alphanumeric sorting, however if you're looking to sort based on attribute, it's time to check out .sort_by.

```
["Penny", "Poki", "Hubble"].sort { |a, b| a <=> b } 
# => ["Hubble", "Penny", "Poki"]
```


**The .sort_by Method**

.sort_by is slightly simpler to implement, but has the potential to be very powerful. This method accepts (it actually requires!) just one parameter. The .sort_by argument represents the element that we want to sort and our parameter will invoke the attribute that we want to sort by. Within the code block, we will define our sole parameter by calling the attribute method or enumerator that we want to sort by, on our argument.

The .sort_by method works by creating a kind of invisible hash. When it's called on an array, it assigns each element a "sort key". Next, .sort_by checks each element against our block, sorts the keys accordingly, and then maps the keys back to their initial values. The return result will be a sorted array. This method is much more dynamic than .sort, with the ability to handle extensive collections and multiple attributes. 

```
["Penny", "Poki", "Hubble"].sort_by { |pet| pet.name } 
# => ["Hubble", "Penny", "Poki"]
```
