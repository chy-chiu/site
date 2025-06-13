---
layout: page
title: Home
permalink: /
---

<div class="intro-section">
  <p class="intro-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
  <p class="intro-text">Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
</div>

<hr class="section-divider">

<section class="recent-posts">
  <h2>Recent Notes</h2>
  <ul class="post-list">
    {% assign sorted_notes = site.notes | sort: 'date' | reverse %}
    {% for note in sorted_notes limit: 5 %}
      <li class="post-item">
        <span class="post-date">{{ note.date | date: "%B %d, %Y" }}</span>
        <a href="{{ note.url | relative_url }}" class="post-title">{{ note.title }}</a>
      </li>
    {% endfor %}
  </ul>
</section>