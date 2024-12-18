---
title: Load YAML Front Matter
project: s4ge
category: log
date: 2024-12-18
---

## Status: done

Done in respect to loading from the poped source.

---

Given the current architecture, implementing front matter should be as easy as loading the yaml in the tasks.

Some front-matter might be config related and so need to be applied or loaded. Others are just passed on to templating and context.

Like in Jekyll and others SSGs, the page should have a `self` key to refer to the page itself. Since this keyword is already in use by Jinja2, we'll use **page**.
