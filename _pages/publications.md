---
title: "Publications"
layout: single
permalink: /publications/
---

{% assign pubs_by_year = site.data.publications | group_by: "year" %}

{% for year in pubs_by_year reversed %}
# {{ year.name }}

  {% for pub in year.items %}

## [{{ pub.title }}]({{ pub.url }})

{% for author in pub.authors %}
  {% assign person = site.people | where: "slug", author | first %}
  [{{ person.title }}]({{ person.url }}){% unless forloop.last %}, {% endunless %}
{% endfor %}

{{ pub.summary }}

  {% endfor %}
{% endfor %}
