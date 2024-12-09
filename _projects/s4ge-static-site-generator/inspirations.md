---
layout: page
title: s4ge - Inspirations
category: index
project: s4ge
---
[gh-actions-jekyll-run]: https://github.com/mrmurilo75/mrmurilo75.github.io/actions/runs/12022286759/workflow
[yaml-info]: https://www.yaml.info/learn/index.html
[Urubu]: https://urubu.jandecaluwe.com/
[al-folio]: https://github.com/alshedivat/al-folio
[pink-space]: https://mrmurilo75.github.io/
[loi-portifolio-figma]: https://www.figma.com/proto/FbKcPFdBjrpp9hY66bOmhF/Portf%C3%B3lio-UX%2FUI?node-id=104-16&t=ULM5E8Qq4uNlbdiv-1
[usetinycms]: https://usetinycms.com
[Obsidian]: https://obsidian.md/


## Ideias

* The context and tags available for the user to use on the source should be heavily limited, for security purposes.
* See **[a Github Actions file][gh-actions-jekyll-run]** for inspirations on the config file format
* To learn more about yaml checkout [yaml.info][yaml-info]

### Future Features

* Precision linking (kinda like how the bible has passages that can be refered with precision. MVC would be linking on hX tags - this requires a tags)
* Backlinkg (Optional)
* Generated Graph of connection (like [Obsidian])

## Inspirations

* [Urubu]
* MVC / MVT Architecture
* Jekyll uses - like [al-folio]
* Use-cases:
    * [My personal site][pink-space]
    * A portifolio / resume site (like [my lovely designer's][loi-portifolio-figma])
    * A customized static site generator (you upload source material, like images and markdown, into a configured instance and it spits out a site applying templates)
* [usetinycms]
    * What we are trying to acomplish is somewhat the "engine" behind this. Except for the writting and the sql (which in our case is the file system), what we are trying to acomplish is the same. We could on top of this build system, have a wysiwyg web-based editor, and have a CI/CD implemented when a user "publishes" a script, which means writing for a buffer structure into the file.
    * The problem with this is that the "fields" (like main content, title, etc are pre-configured). The pure markdown cannot link to another article without hard linking of live. Advanced function, like listing all post linked to an author, are only doable if pre-implemented or using a templating engine, like Jekyl uses Liquid and extends it.

> It turns out I have come up with the same solution as [Urubu]. Looking at their docs they came up with **Markdown content with Jinja2** that's then **rendered into a Jinja2 HTML template**.
