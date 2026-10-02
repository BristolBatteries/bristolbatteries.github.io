---
title: "Publications"
permalink: /publications/
layout: page
description: "Research outputs from the Bristol Energy Systems group."
---

{% assign pubs_by_year = site.data.publications | group_by: "year" | sort: "name" | reverse %}

{% for year_group in pubs_by_year %}
<div class="pub-year-group">
  <h2 class="pub-year-heading">{{ year_group.name }}</h2>
  <div class="pub-list">
    {% for pub in year_group.items %}
    <div class="pub-item">

      <p class="pub-title">
        <a href="{{ pub.url }}" target="_blank" rel="noopener">{{ pub.title }}</a>
      </p>

      <p class="pub-authors">
        {% for author in pub.authors %}
          {% assign ap = site.people | where: "slug", author | first %}
          {% if ap %}
            <a href="{{ ap.url | relative_url }}">{{ ap.title }}</a>{% unless forloop.last %}, {% endunless %}
          {% else %}
            {{ author }}{% unless forloop.last %}, {% endunless %}
          {% endif %}
        {% endfor %}
      </p>

      {% if pub.summary %}
        <p class="pub-summary">{{ pub.summary }}</p>
      {% endif %}

      {% if pub.themes %}
      <div class="mt-2">
        {% for tid in pub.themes %}
          {% for t in site.research_themes %}
            {% if t.id == tid %}
              <span class="badge badge-{{ tid }}">{{ t.name }}</span>
            {% endif %}
          {% endfor %}
        {% endfor %}
      </div>
      {% endif %}

    </div>
    {% endfor %}
  </div>
</div>
{% endfor %}
