---
layout: default
title: Welcome!
description: Welcome to SteveD3's personal portal. The website is unrelated to Technical Outcast, but will be used to discuss research, life, or anything else that doesn't really fit, or is too long for Twitter.
---
Welcome to my little personal portal.

This website is unrelated to [Technical Outcast](https://TechnicalOutcast.com "Technical Outcast is the home of my podcast"), and will be used to discuss research, life, or anything else that comes to mind. [This post should explain it nicely.](https://steved3.io/data/How-I-Spent-My-Pandemic-Vacation/2020/12/31/ "How I Spent My Pandemic Vacation") Mostly, this domain will be used for things that are just too long for Twitter.

Checkout the links below for the most recent articles. Use the Topics link above to see everything.
<hr>
<table>
  {% for post in site.posts limit:4 %}
  <tr>
    <td>{{ post.date | date_to_string }}</td>
    <td><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></td>
  </tr>
  {% endfor %}
</table>
