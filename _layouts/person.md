---
layout: single
---

{{ content }}

{% capture page_md %}

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



{% assign slug = page.slug %}
{% assign pubs = site.data.publications | default: empty %}
{% assign pubs = pubs | sort: "year" | reverse %}

{% assign found = false %}
{% for pub in pubs %}
{% if pub.authors contains slug %}
{% assign found = true %}
{% break %}
{% endif %}
{% endfor %}

{% if found %}
## Relevant publications
{% for pub in pubs %}
{% if pub.authors contains slug %}
* [{{ pub.title }}]({{ pub.url }}) ({{ pub.year }})
  {% endif %}
  {% endfor %}
  {% endif %}

{% endcapture %}

{{ page_md | markdownify }}

