---
layout: page
title: Welcome!
description: Welcome to SteveD3's personal portal. The website is unrelated to Technical Outcast, but will be used to discuss research, life, or anything else that doesn't really fit, or is too long for Twitter.
---
Welcome to my little personal portal. This website is unrelated to [Technical Outcast](https://TechnicalOutcast.com "Technical Outcast is the home of my podcast"), and will be used to discuss research, life, or anything else that comes to mind. Mostly, this domain will be used for things that are just too long for Twitter, but not exactly something that would go on the other domain.

Checkout the links below for the most recent articles.
<hr>
<ul class="list pa0">
  {% for post in site.posts limit:2 %}
  <li class="mv2">
    <a href="{{ site.url }}{{ post.url }}" class="db pv1 link blue hover-mid-gray">
      <time class="fr silver ttu">{{ post.date | date_to_string }} </time>
      {{ post.title }}
    </a>
  </li>
  {% endfor %}
</ul>
