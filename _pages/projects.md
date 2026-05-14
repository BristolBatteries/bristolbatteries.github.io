---
title: "Projects"
layout: single
permalink: /projects/
---

## Current Projects

<div class="projects-grid">
{% assign current = site.projects | where: "status", "current" %}
{% for p in current %}
  {% include project-card.html project=p %}
{% endfor %}
</div>

## Past Projects

<div class="projects-grid">
{% assign past = site.projects | where: "status", "past" %}
{% for p in past %}
  {% include project-card.html project=p %}
{% endfor %}
</div>
