---
layout: post
title:      "Datapond, Jquery and Rails"
date:       2019-06-12 11:54:43 +0000
permalink:  datapond_jquery_and_rails
---


Datapond is a platform for sharing news and market data to facilitate analytics, built on Rails. Now I'm adding jquery to make it a more dynamic application. 

So far, I've added jquery to the data packages' index page, show page and after submitting a form. Though the form submission part is a little slow, it does work... kinda. User creates a data package, the new object's name renders back to that page. Must refactor later! 

The next thing to do is to render a has_many relationship. 

There's a few different ways to maybe accomplish this. 

One possibility is to get a loop going that iterates over this.documents (this being the data package and documents being the array of documents (also arrayed) that the data package possesses). 

I want to access the name field within that nested array, so I think I would need to either do a nested loop (ew) OR a much easier, but hardcoded this.documents[0].name situation OR using a higher order function in the underscore.js library (somthing completely new to me) OR doing something in between a loop and hardcoding. A data package can have an unlimited number of documents, so hardcoding this would be particularly not great code. But maybe I can do an array reduce and access the "name" key for that inner array. 

I've tried the nested loop (mistake!) and the hardcoding (just to check that it works). So the next thing I'm going to try is the array reduce/ access key thought process. 

Ideally, once I've graduated, I'm hoping to build Datapond into a much more dynamic site, with a total of 3-4 pages instead of the current app with 10- 12 pages. Less clicks & page refreshes = better user experience! 


