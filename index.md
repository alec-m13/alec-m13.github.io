---
layout: default
---

It's always good to learn new things, especially things which are interesting. You never know when something you learn will come in handy later on.

There are so many technologies out there. I have taken a crack at learning a few of them:

{% for home in site.homes %}
<h1><a href="{{ home.url }}">{{ home.title }}</a></h1>
<p>{{ home.description }}</p>
{% endfor %}
