---
title: "Projects"
permalink: /projects/
layout: page
description: "Research projects across the Bristol Energy Systems group."
---

{% assign current = site.projects | where: "status", "current" %}
{% assign past    = site.projects | where: "status", "past" %}

{% if current.size > 0 %}
<div class="projects-group">
  <h2 class="projects-group-header">Active Projects</h2>
  <div class="projects-grid">
    {% for project in current %}
      {% include project-card.html project=project %}
    {% endfor %}
  </div>
</div>
{% endif %}

{% if past.size > 0 %}
<div class="projects-group">
  <h2 class="projects-group-header">Completed Projects</h2>
  <div class="projects-grid">
    {% for project in past %}
      {% include project-card.html project=project %}
    {% endfor %}
  </div>
</div>
{% endif %}
