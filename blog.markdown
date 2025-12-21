---
layout: default
title: Blog
permalink: /blog/
---

# Blog

A collection of things I’ve written over time.

Some pieces are about work and systems.  
Some are about technology, parenting, and learning.  
All of them helped me think.

## Articles

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}
