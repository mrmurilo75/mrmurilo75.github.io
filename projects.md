---
layout: page
title: Projects
permalink: /projects/
---

## Projects

{% assign entries = site.projects | where: "entry", true %}
{% for entry in entries %}
* [{{entry.title}}]({{entry.url}})
{% endfor %}

