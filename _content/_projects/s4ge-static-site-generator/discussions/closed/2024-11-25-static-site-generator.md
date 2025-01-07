---
title: Inception
category: discussion
project: s4ge
date: 2024-11-25
open: false
---
[commonmark]: https://commonmark.org/
[Jinja2]: https://jinja.palletsprojects.com/en/stable/
[doit]: https://pydoit.org/

## S4G

Stupidly Simple Static Site Generator.

Write in [Markdown][commonmark] (with [Jinja2]) and outputs to HTML.

The basic structure for a project is:

```
_content/
└── YourContent/...
_templates/
_config.yaml
...
```

## Workflow

1. Load configurations
2. Run Jinja2 on `_content/`, writes to `_markdown/`
3. Run markdown engine on `_markdown/`, writes to `_markup/`
4. Apply `_markup/` Jinja2's `_templates/`, writes to `_site/`

---

## Why

The main motivator to create my own solution is for it to be **only a static site generator**, instead of a blogging engine or CMS. This means delegating wherever possible, implementing only the glue necessary for all the pieces to work nicely and output the site.

The workflow that I have identified so far is:

1. Pre-process structure - extract variables (like the fornt matter in Jekyll)
2. Process content files into HTML
3. Evaluate variables
4. Apply templates

## Tools

* Jinja2 for templating
* docutils to process .md or .rst into html
* Python's [doit] for (re)processing incremental changes

## Features TO Implement

* Queryable file structure

## Questions - Investigate

* Can Jinja2 Template tags/variables etc be used in the content without issues, then be processed when applying template? Would this create security issues - and if so how could we sandbox it.

---

## Idea: Variables

### In a separate file

I could do the vairables in a separate .yaml file, where the settings for each directory or file cascade. This is a way to have *"front matter"*-like variables but without having to extract them from the files, and without polluting the files.

## Features

### Queryable File Structure

There should be a pre-process hook to replace a given function on something with, for example, names of files from a file.

Think of the case where you want to make a list of all files in a sub-directory - like project's logs.

---

## Discussion

### Why not .rst?

It is not a common format. Although it's nice, it is a format specifically made for python documentation and bound to docutils.
