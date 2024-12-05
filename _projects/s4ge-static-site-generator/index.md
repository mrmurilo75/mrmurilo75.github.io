---
layout: page
title: s4ge - Static Site Generator
category: index
project: s4ge
---
[s4ge]: https://github.com/mrmurilo75/s4ge-static-site-generator
[gh-actions-jekyll-run]: https://github.com/mrmurilo75/mrmurilo75.github.io/actions/runs/12022286759/workflow
[yaml-info]: https://www.yaml.info/learn/index.html
[Urubu]: https://urubu.jandecaluwe.com/
[al-folio]: https://github.com/alshedivat/al-folio
[personal-blog]: https://mrmurilo75.github.io/
[loi-portifolio-figma]: https://www.figma.com/proto/FbKcPFdBjrpp9hY66bOmhF/Portf%C3%B3lio-UX%2FUI?node-id=104-16&t=ULM5E8Qq4uNlbdiv-1
[usetinycms]: https://usetinycms.com
[s4ge-poc-commit]: https://github.com/mrmurilo75/s4ge-static-site-generator/commit/05fb6f0239946279873641da4a4faa3661742b29


A **S**tupidly **S**imple **S**tatic **S**ite **Ge**nerator. Write, Process, HTML.

> Follow the development on the [official repository][s4ge].

---

## Why another static site generator?

There are no solutions written in Python that are simply a static site generator! The available options are focused on blogging and architected for it. If there's your goal, you might want to check them out.

The goal of this project is to be a light-weight and extensible solution. Simply **process your source** then **output a website**!

---

## Status

* **Proof Of Concept** is now **deployed**! Check out the [final commit][s4ge-poc-commit] and see [deployed example][s4ge-deployed] (might be of a later version).

### Continue at:

- [ ] Create discussion for MVC
    - Create a Jekyll compatible version
    - Migrate [personal blog][personal-blog] to it

---

## Ideias

* The context and tags available for the user to use on the source should be heavily limited, for security purposes.
* See **[a Github Actions file][gh-actions-jekyll-run]** for inspirations on the config file format
* To learn more about yaml checkout [yaml.info][yaml-info]

## Inspirations

* [Urubu]
* MVC / MVT Architecture
* Jekyll uses - like [al-folio]
* Use-cases:
    * [My personal site][personal-blog]
    * A portifolio / resume site (like [my lovely designer's][loi-portifolio-figma])
    * A customized static site generator (you upload source material, like images and markdown, into a configured instance and it spits out a site applying templates)
* [usetinycms]
    * What we are trying to acomplish is somewhat the "engine" behind this. Except for the writting and the sql (which in our case is the file system), what we are trying to acomplish is the same. We could on top of this build system, have a wysiwyg web-based editor, and have a CI/CD implemented when a user "publishes" a script, which means writing for a buffer structure into the file.
    * The problem with this is that the "fields" (like main content, title, etc are pre-configured). The pure markdown cannot link to another article without hard linking of live. Advanced function, like listing all post linked to an author, are only doable if pre-implemented or using a templating engine, like Jekyl uses Liquid and extends it.

> It turns out I have come up with the same solution as [Urubu]. Looking at their docs they came up with **Markdown content with Jinja2** that's then **rendered into a Jinja2 HTML template**.

---

### Discussions

{% assign discussions = site.projects | where: "project", page.project | where: "category", "discussion" %}

#### Open

{% assign is_open = discussions | where: "open", true %}
{% for discussion in is_open %}
* [{{discussion.title}}]({{discussion.url}})
{% endfor %}

#### Closed

{% assign closed = discussions | where: "open", false %}
{% for discussion in closed %}
* [{{discussion.title}}]({{discussion.url}})
{% endfor %}

---

## Monitoring

### Logs

{% assign logs = site.projects | where: "project", page.project | where: "category", "log" %}
{% for log in logs %}
* [{{ log.date | date: "%Y-%m-%d" }} {{log.title}}]({{log.url}})
{% endfor %}

---

## Review

### Reports

{% assign reports = site.projects | where: "project", page.project | where: "category", "report" %}
{% for report in reports %}
* [{{ report.date | date: "%Y-%m-%d" }} \| {{report.title}}]({{report.url}})
{% endfor %}

