---
layout: page
title: Curso-Dev by Filipe Deschamps
category: index
project: curso-dev
---
[curso.dev]: https://curso.dev
[clone-tabnews repo]: https://github.com/mrmurilo75/clone-tabnews

{% assign entries = site.projects | where: "project", "curso-dev" %}


This "project" is the space where I'll follow along the classes from Filipe Deschamps' course [curso.dev].

The course's project is developed at [clone-tabnews repo].

## Classes Notes

As classes are separated by day, each class will have its own note. Ideally with a TLDR and sections for each topic or sub-classes, so these can be referenced later on.

{% assign classes = entries | where: "category", "class-note" %}
{% for class in classes %}
* [{{class.title}}]({{class.url}})
{% endfor %}