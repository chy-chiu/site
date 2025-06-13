---
layout: page
title: Writing
permalink: /writing/
---

# Writing
Random thoughts and stuff

<hr class="section-divider">

{% assign sorted_notes = site.notes | sort: 'date' | reverse %}
{% for note in sorted_notes %}
   <article href="{{ note.url | relative_url }}" class="writing-post">
    <span class="post-date">{{ note.date | date: "%B %d, %Y" }}</span>
    <a href="{{ note.url | relative_url }}" class="post-title">{{ note.title }}</a>
    <div class="post-content"> 
      {% if forloop.first %}
        {{ note.content }}
      {% else %}
        {{ note.excerpt | default: note.caption | strip_html | truncatewords: 30 }}
      {% endif %}</div>
  </article>
  {% unless forloop.last %}<hr class="writing-divider">{% endunless %}
{% endfor %}