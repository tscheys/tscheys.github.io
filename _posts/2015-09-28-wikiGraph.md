---
layout: post
title: Personal Project: Wikigraph
---
I wanted to make something that gives you a higher order view 
of how different Wikipedia pages are linked together. I made this website during my time at [Hackreactor](www.hackreactor.com). Since I only had two days, I had to zone in on a particular type of page. Since I've always had a hard time visualizing the link between monarchs and their successors, that is exactly what I built!

##Type in "Henry VIII" on [Wikigraph](https://tscheys.github.io/wiki-graph):

![wiki-graph](https://tscheys.github.io/images/wikiGraph.png)

##How it works (Wikipedia API + JQuery + d3):
Wiki-graph uses Wikipedia's search API. Once it has found the page, it reads the HTML (via an ajax call) and looks for the "successor" field in the infobox. This piece of text will point to another wikipedia page. Wikigraph will then make an ajax call to the successor's page. You could look at it as a recursive ajax call. At the end of every ajax call, we pass down the data to d3. This allows us to render something for the user while we are fetching the extra data. The original goal of using d3 was to render some kind of graph visualization (which was out of reach for the time I was given). 

