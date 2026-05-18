---
layout: single
---

{{ content }}

{% if page.email or page.github or page.orcid %}

## Links

{% if page.email %}
- Email: [{{ page.email }}](mailto:{{ page.email }})
{% endif %}

{% if page.github %}
- GitHub: [{{ page.github }}](https://github.com/{{ page.github }})
{% endif %}

{% if page.orcid %}
- ORCID: [{{ page.orcid }}](https://orcid.org/{{ page.orcid }})
{% endif %}

{% endif %}

## Publications

{% assign slug = page.slug %}
{% assign found = false %}

{% assign pubs = site.data.publications | default: empty %}
{% assign pubs = pubs | sort: "year" | reverse %}

{% for pub in pubs %}

{% if pub.authors contains slug %}
{% assign found = true %}

- [{{ pub.title }}]({{ pub.url }}) ({{ pub.year }})

{% endif %}

{% endfor %}

{% unless found %}

No publications listed yet.

{% endunless %}
