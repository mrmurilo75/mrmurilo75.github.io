---
layout: page
title: Personal Blog
category: index
project: personal-blog
---
[welcome-to-jekyll]: {% post_url 2024-09-17-welcome-to-jekyll---by-me %}

## Planning 

### Goals

This site is a hub of knowledge for myself. Not only will I write studies/posts, but I plan on having most - if not all - the information that can be shared in here. It might be too ambitious, but we should always **strive for greatness**. In light of this objective, I'll keep this page as a tracker for the next change to be made to this site.

### Scope

> * Project tracking and planning
> * Notetaking
> * Reference keeping and creating
> * Inspirations referencing

### Roadmap

#### Near future

[ ] CV Page

#### Far Future

[ ] Custom Layout
    * Collapsible listings

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
