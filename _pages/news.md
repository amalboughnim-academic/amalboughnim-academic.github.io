---
layout: page
title: News
permalink: /news/
---

<ul class="news-list">
  {% assign sorted_news = site.news | sort: "date" | reverse %}
  {% for item in sorted_news %}
  <li>
    <span class="news-date">{{ item.date | date: "%B %-d, %Y" }}</span>
    <div class="tag-row">
  {% for tag in item.tags %}
  <span class="tag-badge" style="background-color: {{ site.data.tag_colors[tag] | default: '#B5A99A' }};">
    {{ tag }}
  </span>
  {% endfor %}
</div>
<h3>{{ item.title }}</h3>
    {{ item.content }}
  </li>
  {% endfor %}
</ul>
