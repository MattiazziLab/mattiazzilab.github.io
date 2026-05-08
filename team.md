---
layout: page
title: Team
subtitle: A curious, collaborative group of scientists working at the intersection of cell biology, genetics, and computation.
---

{% assign pi = site.data.team | where: "role", "Principal Investigator" | first %}
{% if pi %}
<div class="pi-spotlight">
  {% if pi.image %}
    <img src="{{ pi.image | prepend: '/assets/images/' | relative_url }}" alt="{{ pi.name }}" class="team-photo" />
  {% else %}
    <div class="team-photo-placeholder">{{ pi.name | slice: 0 }}</div>
  {% endif %}
  <div class="pi-details">
    <div class="team-role">{{ pi.role }}</div>
    <h2 class="team-name" style="font-size:1.75rem; margin-bottom:1rem;">{{ pi.name }}</h2>
    <p class="team-bio">{{ pi.bio }}</p>
    {% if pi.links %}
    <div class="team-links" style="margin-top:1.25rem;">
      {% if pi.links.scholar %}<a href="{{ pi.links.scholar }}" target="_blank" rel="noopener">📄 Google Scholar</a>{% endif %}
      {% if pi.links.twitter %}<a href="{{ pi.links.twitter }}" target="_blank" rel="noopener">🐦 Twitter/X</a>{% endif %}
      {% if pi.links.github  %}<a href="{{ pi.links.github }}"  target="_blank" rel="noopener">💻 GitHub</a>{% endif %}
      {% if pi.links.email   %}<a href="mailto:{{ pi.links.email }}">✉️ Email</a>{% endif %}
    </div>
    {% endif %}
  </div>
</div>
{% endif %}

<span class="section-label">Lab members</span>

<div class="team-grid">
  {% assign members = site.data.team | where_exp: "m", "m.role != 'Principal Investigator'" | where_exp: "m", "m.alumni == nil" %}
  {% for member in members %}
  <div class="team-card">
    {% if member.image %}
      <img src="{{ member.image | prepend: '/assets/images/' | relative_url }}"
           alt="{{ member.name }}" class="team-photo" />
    {% else %}
      <div class="team-photo-placeholder">{{ member.name | slice: 0 }}</div>
    {% endif %}
    <div class="team-info">
      <div class="team-role">{{ member.role }}</div>
      <div class="team-name">{{ member.name }}</div>
      <p class="team-bio">{{ member.bio }}</p>
      {% if member.links %}
      <div class="team-links">
        {% if member.links.scholar   %}<a href="{{ member.links.scholar }}"   target="_blank" rel="noopener">📄 Scholar</a>{% endif %}
        {% if member.links.twitter   %}<a href="{{ member.links.twitter }}"   target="_blank" rel="noopener">🐦 Twitter</a>{% endif %}
        {% if member.links.github    %}<a href="{{ member.links.github }}"    target="_blank" rel="noopener">💻 GitHub</a>{% endif %}
        {% if member.links.linkedin  %}<a href="{{ member.links.linkedin }}"  target="_blank" rel="noopener">🔗 LinkedIn</a>{% endif %}
        {% if member.links.website   %}<a href="{{ member.links.website }}"   target="_blank" rel="noopener">🌐 Website</a>{% endif %}
        {% if member.links.email     %}<a href="mailto:{{ member.links.email }}">✉️ Email</a>{% endif %}
      </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>

{% assign alumni = site.data.team | where: "alumni", true %}
{% if alumni.size > 0 %}
<h2 class="section-label" style="margin-top: 3rem;">Alumni</h2>

<div class="alumni-list">
  {% for person in alumni %}
  <div class="alumni-entry">
    <span class="alumni-name">{{ person.name }}</span><span class="alumni-sep"> &middot; </span><span class="alumni-meta">{{ person.role }}{% if person.years %}, {{ person.years }}{% endif %}</span>
  </div>
  {% endfor %}
</div>
{% endif %}

---

## Interested in joining?

We are always looking for motivated researchers. See our [Contact page]({{ '/contact' | relative_url }}) for open positions and how to get in touch.
