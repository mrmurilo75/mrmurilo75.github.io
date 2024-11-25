---
layout: page
title: Static Site Generator
category: index
project: static-site-generator
---
[doit]: https://pydoit.org/

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
