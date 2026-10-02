---
title: "Research"
permalink: /research/
layout: page
description: "Research themes in the Bristol Energy Systems group."
---

Our group works across three interconnected research themes. Each theme links to dedicated pages showing the people, projects, and publications in that area.

<div class="theme-cards" style="margin-top:2rem;">
{% for theme in site.research_themes %}
<div class="theme-card">
  <div class="theme-card-bar" style="background:{{ theme.color }};"></div>
  <div class="theme-card-body">
    <div class="theme-card-icon">{{ theme.icon }}</div>
    <h3 class="theme-card-title">{{ theme.name }}</h3>
    <p class="theme-card-desc">{{ theme.description }}</p>
    <a href="{{ theme.url | relative_url }}" class="theme-card-link" style="color:{{ theme.color }};">Explore &rarr;</a>
  </div>
</div>
{% endfor %}
</div>
