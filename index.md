---
layout: default
title: Home
---

{% include hero.html %}

<!-- Highlight cards -->
<section class="home-highlights">
  <div class="container">
    <span class="section-label">What we do</span>
    <div class="highlights-grid">
      <a href="{{ '/research' | relative_url }}" class="highlight-card">
        <div class="hi-icon">🔬</div>
        <h3>Phenotypic Heterogeneity</h3>
        <p>Coming soon.</p>
      </a>
      <a href="{{ '/research' | relative_url }}" class="highlight-card">
        <div class="hi-icon">🫧</div>
        <h3>Regulation of Endocytosis</h3>
        <p>Coming soon.</p>
      </a>
      <a href="{{ '/research' | relative_url }}" class="highlight-card">
        <div class="hi-icon">⏳</div>
        <h3>Interorganelle Communication and Cellular Aging</h3>
        <p>Coming soon.</p>
      </a>
    </div>

  </div>
</section>

<!-- Recent news -->
<section class="home-news">
  <div class="container">
    <span class="section-label">Latest</span>
    <h2 class="section-title">News &amp; Updates</h2>
    <div class="news-list-home">
      {% assign recent_news = site.data.news | sort: "date" | reverse | limit: 3 %}
      {% for item in recent_news %}
      <div class="news-item-home">
        <span class="news-date">{{ item.date | date: "%b %Y" }}</span>
        <div>
          <h3>{{ item.title }}</h3>
          <p>{{ item.body }}</p>
        </div>
      </div>
      {% endfor %}
    </div>
    <div style="margin-top: 2rem;">
      <a href="{{ '/news' | relative_url }}" class="btn btn-secondary">All news →</a>
    </div>
  </div>
</section>
