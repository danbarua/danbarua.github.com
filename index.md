---
layout: page
title: Dan Barua
tagline: Insert witty tagline here
---
{% include JB/setup %}

I'm a developer, I write code and stuff.

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>