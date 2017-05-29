---
layout: post
title: How to Resolve Server Failed to Start for Port 8080 Grails
tags: [Grails, Linux]
---

There are time when the port number of 8080 is already used and we want to use the same port. In linux, the way we kill the process is by issued the command
{% highlight javascript linenos %}
lsof -w -n -i tcp:8080
{% endhighlight %}
