---
title: "People"
layout: single
permalink: /people/
classes: wide
---

{% assign desired_groups = "Academic Staff|Postdoctoral Researchers|PhD Students" | split: "|" %}

{% for group_name in desired_groups %}

{% assign people_in_group = site.people | where: "group", group_name %}

{% if people_in_group.size > 0 %}

# {{ group_name }}

<div class="grid__wrapper">

{% for person in people_in_group %}

{% if person.status != "previous" %}

<div class="grid__item">
  <article class="archive__item" style="text-align:center; padding:1rem; height:100%;">

    {% if person.image %}
      <img src="{{ person.image | relative_url }}"
           alt="{{ person.title }}"
           style="width:180px;height:180px;object-fit:cover;border-radius:50%;margin-bottom:1rem;">
    {% endif %}

    <h2 class="archive__item-title">
      <a href="{{ person.url | relative_url }}">
        {{ person.title }}
      </a>
    </h2>

    {% if person.role %}
      <p><strong>{{ person.role }}</strong></p>
    {% endif %}

    {% if person.excerpt %}
      <p>{{ person.excerpt }}</p>
    {% endif %}

  </article>
</div>

{% endif %}
{% endfor %}

</div>

<div style="clear: both;"></div>

{% endif %}

{% endfor %}


{% assign previous_people = site.people | where: "status", "previous" %}

{% if previous_people.size > 0 %}

---

# Previous Members

<div class="grid__wrapper">

{% for person in previous_people %}

<div class="grid__item">
  <article class="archive__item" style="text-align:center; padding:1rem; height:100%; opacity:0.7;">

    {% if person.image %}
      <img src="{{ person.image | relative_url }}"
           alt="{{ person.title }}"
           style="width:150px;height:150px;object-fit:cover;border-radius:50%;margin-bottom:1rem;">
    {% endif %}

    <h3 class="archive__item-title">
      <a href="{{ person.url | relative_url }}">
        {{ person.title }}
      </a>
    </h3>

    {% if person.role %}
      <p><strong>{{ person.role }}</strong></p>
    {% endif %}

  </article>
</div>

{% endfor %}

</div>

{% endif %}
