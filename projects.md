---
layout: page
title: Projects
permalink: /projects/
---

## Projects

{% assign entries = site.projects | where: "category", "index" %}
{% for entry in entries %}
* [{{entry.title}}]({{entry.url}})
{% endfor %}


## Project Structures

```
_projects/ <- You are here
└── [project]/
    ├── project_index
    ├── [feature]/
    │   ├── feature_index (with planned work and tracking)
    │   └── logs/
    ├── logs/
    ├── reports/
    └── discussions/
        └── closed/
```

### Planning

Each project will have an **index page** containing general information. If a project is just an ideia, this page can outline motivation and link to inspirations. 

Once a project begins to grow and has a more concrete plan, those ideas and references will be kept into the **discussions folder**. This is a free space to take notes, keep inspirations, and think of next steps. From these will come the decisions on which features to implement, define priorities, etc.

To keep things clean and clear, there will be a **conclusions section**. In case the conclusion is to implement a feature, a plan needs to be laid out. This can be done directly in the conclusion section for simpler features or by creating a substructure, with it's own index page containing the plan. 

### Monitoring

During implementation the smaller decisions (such as whether to implement using X or Y design pattern), references, and other information should be noted in **the logs**. These are the real-life save files. They should have all the information necessary to pick back up where you left - even if starting from a blank workspace.

### Reviewing

Once a feature is implemented or a milestone is reached, the logs should be **revised into a report**. Reviewing relevant information, code snippets, time spent, what went right and what might have been better if done differently. The reports should provide a **concise view of the work** done and serve as a **reference for similar work** in the future.