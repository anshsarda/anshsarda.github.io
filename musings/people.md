---
layout: default
nav: musings
title: People
permalink: /musings/people/
---

<div class="top-links"><a href="{{ "/musings/" | prepend: site.baseurl }}">back</a></div>

<hr class="entry-divider">

{% assign topic_posts = site.musings | where: "topic", "people" | sort: "date" | reverse %}
{% for post in topic_posts %}
<div class="entry">
  <a class="entry-title" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  <span class="entry-date">{{ post.date | date: "%m/%d/%y" }}</span>
</div>
<hr class="entry-divider">
{% endfor %}
