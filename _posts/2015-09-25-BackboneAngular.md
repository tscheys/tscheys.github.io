---
layout: post
title: Angular versus Backbone in lines of code
---
##Introduction

In this post we will do a quick comparison of how many lines of code you are 
actually importing into your project when adding a framework. 

Running ```bower install angular``` or ```bower install backbone``` is just a few keystrokes away. Sometimes 
you do not realize how this effects the performance of your app. Seeing how big these frameworks 
are in terms of size/lines of code makes you ask yourself the question: do we really need it?

##Number of lines 

- Angular: > 20.000
- Backbone: 1.900

This is a comparison you might have seen. In my opinion this is not a fair assessment. Backbone requires
you to also install Underscore and JQuery.

- JQuery: 9.000
- Underscore: 1.500

So this makes the whole Backbone framework weigh in at about:

- Backbone: 1.900 + 9.000 (JQuery) + 1.500 (Underscore) = 12.400 lines of code

In summary we get a more fair comparison with:

- Angular: > 20.000
- Backbone: 12.400

It is fair to say that Backbone is about half the size of Angular.

Most of the time you do not even need a full framework and you can just use JQuery. And even then
you sometimes don't even really need JQuery as this website proves: [http://youmightnotneedjquery.com/](http://youmightnotneedjquery.com/)!