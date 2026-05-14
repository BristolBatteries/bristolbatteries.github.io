---
title: "People"
layout: single
permalink: /people/
classes: wide
---

<div class="grid__wrapper">

{% assign sorted_people = site.people | sort: "title" %}

{% for person in sorted_people %}

<div class="grid__item">
  <article
    class="archive__item"
    style="
      text-align:center;
      padding:1rem;
      height:100%;
    "
  >

    {% if person.image %}
      <img
        src="{{ person.image | relative_url }}"
        alt="{{ person.title }}"
        style="
          width:180px;
          height:180px;
          object-fit:cover;
          border-radius:50%;
          margin-bottom:1rem;
        "
      >
    {% endif %}

    <h2 class="archive__item-title">
      <a href="{{ person.url | relative_url }}">
        {{ person.title }}
      </a>
    </h2>

    {% if person.role %}
      <p>
        <strong>{{ person.role }}</strong>
      </p>
    {% endif %}

    {% if person.excerpt %}
      <p>{{ person.excerpt }}</p>
    {% endif %}

  </article>
</div>

{% endfor %}

</div>
