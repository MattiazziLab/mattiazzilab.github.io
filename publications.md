---
layout: page
title: Publications
subtitle: Our publications.
---

{% assign sorted_pubs = site.data.publications | sort: "year" | reverse %}
{% assign years = sorted_pubs | map: "year" | uniq %}

{% for year in years %}
<div class="publications-year-group">
  <h2 class="pub-year-heading">{{ year }}</h2>
  <div class="pub-list">
    {% assign year_pubs = sorted_pubs | where: "year", year %}
    {% for pub in year_pubs %}
    <div class="pub-entry">
      <div class="pub-title">
        {% if pub.link %}
          <a href="{{ pub.link }}" target="_blank" rel="noopener">{{ pub.title }}</a>
        {% else %}
          {{ pub.title }}
        {% endif %}
      </div>
      <div class="pub-authors">{{ pub.authors | markdownify | remove: '<p>' | remove: '</p>' | strip }}</div>
      <div class="pub-venue">{{ pub.journal }}{% if pub.year %}, {{ pub.year }}{% endif %}</div>
      <div class="pub-links">
        {% if pub.link %}<a href="{{ pub.link }}" target="_blank" rel="noopener">PubMed</a>{% endif %}
        {% if pub.doi  %}<a href="https://doi.org/{{ pub.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
        {% if pub.preprint %}<a href="{{ pub.preprint }}" target="_blank" rel="noopener">Preprint</a>{% endif %}
      </div>
      {% if pub.tags %}
      <div style="margin-top: 0.75rem; display: flex; gap: 0.4rem; flex-wrap: wrap;">
        {% for tag in pub.tags %}<span class="tag">{{ tag }}</span>{% endfor %}
      </div>
      {% endif %}
    </div>
    {% endfor %}
  </div>
</div>
{% endfor %}

---

<p style="font-size:0.875rem; color: var(--dark-400, #94a3b8);">
  For the most current list, see
  <a href="https://scholar.google.com/citations?user=rsTE7ncAAAAJ&hl=en" target="_blank" rel="noopener">Google Scholar</a>.
</p>
