---
title: Proof Of Concept
project: s4ge
category: log
date: 2024-12-05
---
[s4ge]: https://github.com/mrmurilo75/s4ge-static-site-generator
[related-commits]: https://github.com/mrmurilo75/s4ge-static-site-generator/commits/main/?since=2024-12-04&until=2024-12-05
[gh-actions-jekyll-run]: https://github.com/mrmurilo75/mrmurilo75.github.io/actions/runs/12022286759/workflow


## Status

### Completed:

> See the [related commits][related-commits]

### Continue at:

- [ ] Test with Github Actions (based on [jekyll's][gh-actions-jekyll-run])

---

## Getting Started

Get started by reading [the discussion][source-discussion]. From there create, read the docs on the relevant tools and play around.

- [X] Create example usage
    - [X] Add `_source`
    - [X] Add `_templates`
- [X] Create Proof Of Concept
    - [X] 1. Parse Markdown to HTML - outputs to `_rendered`
    - [X] 2. Apply to Jinja2 templates - outputs to `_site`
    - [X] 3. Write build process with **doit**
- [ ] Test with Github Actions (based on jekyll's)

---

## Administration

- [ ] Replicate these development tracking and decisions in the issues/milestones of the [official repo][s4ge]

---

## Notes

### Proof Of Concept

#### Mistletoe

```python
import mistletoe

SOURCE = '_source/index.md'
DESTINATION = '_rendered/index.html'

with open(SOURCE, 'r') as fin:
    rendered = mistletoe.markdown(fin)

with open(DESTINATION, 'w') as fout:
    fout.write(rendered)
```

#### Jinja

```python
from jinja2 import Environment, FileSystemLoader

SOURCE = '_rendered/index.html'
DESTINATION = '_site/index.html'

TEMPLATES_FOLDER = '_templates/'
TEMPLATE = 'index.html'

env = Environment(loader=FileSystemLoader(TEMPLATES_FOLDER))
template = env.get_template(TEMPLATE)

context = {}
with open(SOURCE, 'r') as fin:
    context["content"] = fin.read()

rendered = template.render(context)

with open(DESTINATION, 'w') as fout:
    fout.write(rendered)
```

#### doit

The default file for **task-creators** function is `dodo.py`:

```python
def task_render_site(): # Task 'render_site'
    return {
        'actions': ['python3 app.py'],
    }
```

To execute the task, run the `doit` command (without arguments it executes all tasks in the `dodo.py` file).
