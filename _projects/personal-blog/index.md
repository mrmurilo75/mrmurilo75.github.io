---
layout: page
title: Personal Blog
category: index
project: personal-blog
---
[welcome-to-jekyll]: {% post_url 2024-09-17-welcome-to-jekyll---by-me %}

## Goals

This site is a hub of knowledge for myself. Not only will I write studies/posts, but I plan on having most - if not all - the information that can be shared in here. It might be too ambitious, but we should always **strive for greatness**. In light of this objective, I'll keep this page as a tracker for the next change to be made to this site.

---

## Planned Work

### In Progress

### Next
* Write log note of adding collections and cheatsheet of used Liquid/Jekyll

### To be discussed
* Layout
* Create CV as a page
* Use folder structure instead of defining 'project' and 'category' front matter
* Investigate plugins

### Done
* Rewrite this page to reflect the indexing of a project
    * [2024-10-10]({% link _projects/personal-blog/log/2024-10-10-2334.md %})

--- 

## Logs

{% assign logs = site.projects | where: "project", page.project | where: "category", "log" %}
{% for log in logs %}
* [{{log.title}}]({{log.url}})
{% endfor %}

--- 

## Progress Reports

{% assign reports = site.projects | where: "project", page.project | where: "category", "report" %}
{% for report in reports %}
* [{{report.title}}]({{report.url}})
{% endfor %}

--- 

## Discussions

{% assign discussions = site.projects | where: "project", page.project | where: "category", "discussion" %}
{% for discussion in discussions %}
* [{{discussion.title}}]({{discussion.url}})
{% endfor %}
