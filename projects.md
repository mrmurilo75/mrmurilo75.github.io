---
layout: page
title: Projects
permalink: /projects/
---

## Projects

{% assign entries = site.projects | where: "category", "index" %}
{% for entry in entries %}
* [{{entry.title}}]({{entry.url}})
{% endfor %}

