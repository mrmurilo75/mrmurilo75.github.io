---
layout: page
title: s4ge - Static Site Generator
category: index
project: s4ge
---
[s4ge]: https://github.com/mrmurilo75/s4ge-static-site-generator
[personal-blog]: https://mrmurilo75.github.io/
[loi-portifolio-figma]: https://www.figma.com/proto/FbKcPFdBjrpp9hY66bOmhF/Portf%C3%B3lio-UX%2FUI?node-id=104-16&t=ULM5E8Qq4uNlbdiv-1
[al-folio]: https://github.com/alshedivat/al-folio


A **S**tupidly **S**imple **S**tatic **S**ite **Ge**nerator. Write, Process, HTML.

> Follow the development on the [official repository][s4ge].

---

## Why another static site generator?

There are no solutions written in Python that are simply a static site generator! The available options are focused on blogging and architected for it. If there's your goal, you might want to check them out.

The goal of this project is to be a light-weight and extensible solution. Simply **process your source** then **output a website**!

---

## Inspirations

* MVC / MVT Architecture
* Jekyll uses - like [al-folio]
* Use-cases:
    * [My personal site][personal-blog]
    * A portifolio / resume site (like [my lovely designer's][loi-portifolio-figma])
    * A customized static site generator (you upload source material, like images and markdown, into a configured instance and it spits out a site applying templates)

### The hard part

What I'm struggling with the most is figuring out how to connect things in source. Like in my own site, I want to list project's which are a subdirectory.

### The simplest setup

Would be for a personal site like my own. Add source markdown with Jinja2 that requires context on the file structure.

So theres a pre-process context gathering, then render Jinja2 markdown, then render HTML from configured Jinja2 templates.

---

## Planning

### Scope

### Roadmap

**version 0.1.0**:

* source in `_source/` written in markdown with Jinja2
* midway markdown in `_prerender/`
* final render applying templates in `_output/`

**Which templates to apply for final rendering?**

Replicate the file structure in `_config.yml` to define templates in a cascading matter.

#### Next Tasks

#### To Be Planned

#### Done

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

