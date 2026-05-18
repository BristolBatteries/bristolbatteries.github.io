---
title: "Publications"
layout: single
permalink: /publications/
---

{% assign pubs_by_year = site.data.publications | group_by: "year" | sort: "name" | reverse %}

{% for year in pubs_by_year %}

## {{ year.name }}

<div class="publications-list">

  {% for pub in year.items %}

  <div class="publication-item">

    <h3 class="publication-title">
      <a href="{{ pub.url }}">{{ pub.title }}</a>
    </h3>

    {% if pub.authors %}
    <p class="publication-authors">
      {% for author in pub.authors %}
        {% assign person = site.people | where: "slug", author | first %}
        {% if person %}
          <a href="{{ person.url }}">{{ person.title }}</a>{% unless forloop.last %}, {% endunless %}
        {% else %}
          {{ author }}{% unless forloop.last %}, {% endunless %}
        {% endif %}
      {% endfor %}
    </p>
    {% endif %}

    {% if pub.summary %}
    <div class="publication-summary">
      {{ pub.summary }}
    </div>
    {% endif %}

  </div>

  {% endfor %}

</div>

<hr>

{% endfor %}
