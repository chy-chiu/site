---
layout: home
title: Writing
permalink: /writing/
---

# Writing

{% assign sorted_notes = site.notes | sort: 'date' | reverse %}
{% for note in sorted_notes %}
  <article class="writing-post">
    <span class="post-date">{{ note.date | date: "%B %d, %Y" }}</span>
    <h2 class="post-title">{{ note.title }}</h2>
    <div class="post-content">{{ note.content }}</div>
  </article>
  {% unless forloop.last %}<hr class="writing-divider">{% endunless %}
{% endfor %}