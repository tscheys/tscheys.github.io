---
layout: post
title: Troubleshooting when deploying your Node.js app
---
This post is mainly a  non-exhaustive list of things that could go wrong when you deploy you app.

##1. You are not listening on the correct port 

In most cases, services like Heroku will make you use a specific port. And in most cases it is
not 8080, 8000 or 3000. This can be taken into account in just one line of code: 
{% highlight javascript %}
var port = 8080;
{% endhighlight %}
becomes
{% highlight javascript %}
var port = process.env.PORT || 8080;
{% endhighlight %}
The process.env.PORT will ensure that the correct port will be set when we deploy. 

##2. Your local npm and node versions are different from those installed on the server

To force the server to install the versions you want you can add the following to your `package.json`: 

{% highlight javascript %}
"engines": {
    "node": "0.12.7",
    "npm": "2.14.2"
  }
{% endhighlight %}

These are the versions that I want to install on the server, because these are the ones I use locally. 

To figure out which version you need to put in, type this in you terminal window: 

`npm -v` and `node -v`

##3. Check your .gitignore when pushing to your server remote

A lot of deployment services make you push to a remote to deploy. This one took 6 hours out of my day to figure out! Do better than I did.

##4. Static files should be in your server folder

Your app should be scaffolded like so: 

{% highlight javascript %}
App
--Server
----Public
------index.html
------css
------img
----index.js
{% endhighlight %}

Where index.js is the script that starts up your server. 

##5. Have an npm start script or Procfile to start your server 

Easiest way to ensure that your server actually executes your server code is to include the following in your package.json: 

{% highlight javascript %}
"scripts": {
  "start": "node server/index.js" 
  }
{% endhighlight %}

##6. A word of encouragement

<iframe src="//giphy.com/embed/RKpZGrXAccvTi?html5=true" width="480" height="514" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="http://giphy.com/gifs/boy-crying-RKpZGrXAccvTi">via GIPHY</a></p>

You are not alone in your suffering. Deployment is HARD. You will probably waste multiple hours on minor issues that do not learn you a lot about deployment. Everybody who learns this stuff has a HARD time at first. 







