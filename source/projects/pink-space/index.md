---
title: Pink Space - My personal website
---

[welcome-to-jekyll]: /_posts/2024-09-17-welcome-to-jekyll---by-me.md
[resume]: /resume.html
[curso-dev_day-5-and-6]: /projects/curso-dev/class-notes/day-5-and-6.html
[curso-dev_day-8-and-9]: /projects/curso-dev/class-notes/day-8-and-9.html
[custom-layout_log]: /projects/pink-space/log/2024-11-15-custom-layout.html
[notebook-notes-groups_log]: /projects/pink-space/log/2024-11-15-notebook-notes-groups.html

## Planning

### Goals

This site is a hub of knowledge for myself. Not only will I write studies/posts, but I plan on having most - if not all - the information that can be shared in here. It might be too ambitious, but we should always **strive for greatness**.

### Scope

-   Planning and tracking projects
-   Note-taking
-   Create reference for repeatable tasks
-   Reference inspirations
-   Software agnostic - content needs to be visible and understandable as plain text

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

[ ] Configuring Github Pages on custom domain

[ ] Git Usage + CheatSheet - based on [these notes][curso-dev_day-5-and-6] from curso-dev

[ ] Gamification of Progress - based on curso-dev notes on [Planning & Tracking][curso-dev_day-8-and-9]

#### Done

[X] Configure custom domain

[X] [CV Page][resume]

[X] [CV Page in Portuguese][resume]

---

### Discussions

#### Open

{% for discussion in pages['projects']['pink-space']['discussions'] %}
    {% if discussion != '_values' %}
        {% if pages['projects']['pink-space']['discussions'][discussion]['_values']['open'] %}

- [{{ discussion.title }}]({{ discussion.path }}.html)

        {% endif %}
    {% endif %}
{% endfor %}

#### Closed

{% for discussion in pages['projects']['pink-space']['discussions'] %}
    {% if discussion != '_values' %}
        {% if pages['projects']['pink-space']['discussions'][discussion]['_values']['open'] %}

- [{{ discussion.title }}]({{ discussion.path }})

        {% endif %}
    {% endif %}
{% endfor %}
