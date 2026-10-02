---
title: "People"
permalink: /people/
layout: page
description: "Meet the Bristol Energy Systems research group."
---

{% assign groups = "Academic Staff|Postdoctoral Researchers|PhD Students" | split: "|" %}

{% for group_name in groups %}
  {% assign members = site.people | where: "group", group_name | where_exp: "p", "p.status != 'previous'" %}
  {% if members.size > 0 %}
<div class="people-group">
  <h2 class="people-group-header">{{ group_name }}</h2>
  <div class="people-grid">
    {% for person in members %}
      {% include person-card.html person=person %}
    {% endfor %}
  </div>
</div>
  {% endif %}
{% endfor %}

{% assign previous = site.people | where: "status", "previous" %}
{% if previous.size > 0 %}
<div class="people-group" style="margin-top:3rem; padding-top:2rem; border-top:1px solid var(--color-border);">
  <h2 class="people-group-header" style="color:var(--color-muted);">Previous Members</h2>
  <div class="people-grid">
    {% for person in previous %}
      {% include person-card.html person=person %}
    {% endfor %}
  </div>
</div>
{% endif %}
