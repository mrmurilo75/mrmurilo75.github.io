---
title: s4ge - Static Site Generator
---
[s4ge]: https://github.com/mrmurilo75/s4ge-static-site-generator
[pink-space]: https://mrmurilo75.github.io/
[s4ge-poc-commit]: https://github.com/mrmurilo75/s4ge-static-site-generator/commit/05fb6f0239946279873641da4a4faa3661742b29
[s4ge-deployed]: https://mrmurilo75.github.io/s4ge-static-site-generator/
[inspirations]: /projects/s4ge-static-site-generator/inspirations.html
[log-mvp]: /projects/s4ge-static-site-generator/logs/2024-12-09-mvp.html
[canceled-mvp]: /projects/s4ge-static-site-generator/discussions/closed/2024-12-09-minimum-viable-product.html


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

{% set discussions = pages['projects']['s4ge-static-site-generator']['discussions'] %}

#### Open

{% for discussion in discussions %}
    {% if discussion != '_values' and discussions[discussion]['_values']['open'] %}

- [{{ discussion.title }}]({{ discussion.path }}.html)

    {% endif %}
{% endfor %}

#### Closed


{% for discussion in discussions %}
    {% if discussion != '_values' and not discussions[discussion]['_values']['open'] %}

- [{{ discussion.title }}]({{ discussion.path }}.html)

    {% endif %}
{% endfor %}
