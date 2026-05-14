---
title: "People"
layout: single
permalink: /people/
---

# Team

{% assign sorted_people = site.people | sort: "title" %}

{% for person in sorted_people %}

## [{{ person.title }}]({{ person.url }})

**{{ person.role }}**

{{ person.excerpt }}

{% endfor %}
