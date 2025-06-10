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
    <div class="post-title">{{ note.title }}</div>
    <div class="post-content"> 
      {% if forloop.first %}
        {{ note.content }}
      {% else %}
        {{ note.excerpt | default: note.caption | strip_html | truncatewords: 30 }}
      {% endif %}</div>
  </article>
  {% unless forloop.last %}<hr class="writing-divider">{% endunless %}
{% endfor %}