---
layout: page
title: News
subtitle: Updates from the Mattiazzi Lab &ndash; new papers, people, and milestones.
---

<div class="news-grid">
  {% assign sorted_news = site.data.news | sort: "date" | reverse %}
  {% for item in sorted_news %}
  <div class="news-card">
    <div class="news-date-badge">
      <span class="ndb-month">{{ item.date | date: "%b %Y" }}</span>
    </div>
    <div class="news-body">
      <h3>{{ item.title }}</h3>
      <p>{{ item.body }}</p>
    </div>
  </div>
  {% endfor %}
</div>
