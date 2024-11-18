---
layout: page
title: Personal Blog
category: index
project: personal-blog
---
[welcome-to-jekyll]: {% link _posts/2024-09-17-welcome-to-jekyll---by-me.md %}
[resume]: {% link resume.html %}
[curso-dev_day-5-and-6]: {% link _projects/curso-dev/class-notes/day-5-and-6.md %}
[curso-dev_day-8-and-9]: {% link _projects/curso-dev/class-notes/day-8-and-9.md %}
[custom-layout_log]: {% link _projects/personal-blog/log/2024-11-15-custom-layout.md %}
[notebook-notes-groups_log]: {% link _projects/personal-blog/log/2024-11-15-notebook-notes-groups.md %}


## Planning

### Goals

This site is a hub of knowledge for myself. Not only will I write studies/posts, but I plan on having most - if not all - the information that can be shared in here. It might be too ambitious, but we should always **strive for greatness**.

### Scope

* Planning and tracking projects
* Note-taking
* Create reference for repeatable tasks 
* Reference inspirations
* Software agnostic - content needs to be visible and understandable as plain text

### Roadmap

#### Next Tasks

[ ] Rewrite this project's [Inception]

[ ] Custom Layout - [In Progress][custom-layout_log]

[ ] Group notes on Notebook - [In Progress][notebook-notes-groups_log]

#### To Be Planned

[ ] Rewrite the Home page's content

[ ] Write the README - Describe the project and explain usage/install

[ ] Further improve the description and structuring of logs, discussion, reports based on curso-dev related [classes on planning and structure][curso-dev_day-8-and-9]

##### Posts

[ ] Git Usage + CheatSheet - based on [these notes][curso-dev_day-5-and-6] from curso-dev

[ ] Gamification of Progress - based on curso-dev notes on [Planning & Tracking][curso-dev_day-8-and-9]

#### Done

[X] [CV Page][resume]
[X] [CV Page in Portuguese][resume]

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
