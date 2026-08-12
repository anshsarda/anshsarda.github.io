---
layout: default
nav: musings
title: Musings
permalink: /musings/
---

<div class="top-links"><a href="{{ "/musings/world/" | prepend: site.baseurl }}">world</a> • <a href="{{ "/musings/food/" | prepend: site.baseurl }}">food</a> • <a href="{{ "/musings/words/" | prepend: site.baseurl }}">words</a> • <a href="{{ "/musings/people/" | prepend: site.baseurl }}">people</a> • <a href="{{ "/musings/self/" | prepend: site.baseurl }}">self</a></div>

<h2 class="section-label">recents</h2>

<hr class="entry-divider">

{% assign cutoff = site.time | date: '%s' | minus: 2592000 %}
{% assign recent_musings = site.musings | where_exp: "p", "p.date | date: '%s' > cutoff" | sort: "date" | reverse %}
{% for post in recent_musings %}
<div class="entry">
  <a class="entry-title" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  <span class="entry-date">{{ post.date | date: "%m/%d/%y" }}</span>
</div>
<hr class="entry-divider">
{% endfor %}
