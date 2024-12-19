---
title: s4ge - Static Site Generator
---
[s4ge]: https://github.com/mrmurilo75/s4ge-static-site-generator
[pink-space]: https://mrmurilo75.github.io/
[s4ge-poc-commit]: https://github.com/mrmurilo75/s4ge-static-site-generator/commit/05fb6f0239946279873641da4a4faa3661742b29
[s4ge-deployed]: https://mrmurilo75.github.io/s4ge-static-site-generator/
[inspirations]: {% link _projects/s4ge-static-site-generator/inspirations.md %}
[log-mvp]: {% link _projects/s4ge-static-site-generator/logs/2024-12-09-mvp.md %}
[canceled-mvp]: {% link _projects/s4ge-static-site-generator/discussions/closed/2024-12-09-minimum-viable-product.md %}


A **S**tupidly **S**imple **S**tatic **S**ite **Ge**nerator. Write, Process, HTML.

> Follow the development on the [official repository][s4ge].

---

## Why another static site generator?

~~There are no solutions written in Python that are simply a static site generator! The available options are focused on blogging and architected for it. If there's your goal, you might want to check them out.~~

~~The goal of this project is to be a light-weight and extensible solution. Simply **process your source** then **output a website**!~~

Because I wanted to do it myself.

---

## Status

### Proof Of Concept

**Proof Of Concept** is now **deployed**! Check out the [final commit][s4ge-poc-commit] and see [deployed example][s4ge-deployed] (might be of a later version).

### Continue at:

- [ ] Create a new log and discussion for development - based on [canceled mvp][canceled-mvp].

---

## Inspirations and Ideas

Check out the [Inspirations and Ideas][inspirations] for future features!

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

