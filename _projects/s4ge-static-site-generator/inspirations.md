---
layout: page
title: s4ge - Inspirations
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
[pelican-search]: https://github.com/pelican-plugins/search
[urubu-template-contructs]: http://urubu.jandecaluwe.com/manual/templating-in-pages.html
[hugo-archtypes]: https://gohugo.io/content-management/archetypes/
[mdBooks]: https://rust-lang.github.io/mdBook/index.html
[gh-actions-wf-examples]: https://github.com/actions/starter-workflows/tree/main/pages/
[Umami]: https://umami.is/


## Ideias

* The context and tags available for the user to use on the source should be heavily limited, for security purposes.
* See **[a Github Actions file][gh-actions-jekyll-run]** for inspirations on the config file format
* To learn more about yaml checkout [yaml.info][yaml-info]

* One directive to be added to the project is that it should be able to be used as a documentation tool, like docutils

* Make it compatible with Obsidian md, so it can be used with the github plugin for sync and, as a side effect, it's up as a site.

### Future Features

* Add Analytics with [Umami] - GDPR open source (and free?)

* Add templates with simple things that can be included in source - see [urubu's feature][urubu-template-contructs]
* Precision linking (kinda like how the bible has passages that can be refered with precision. MVC would be linking on hX tags - this requires a tags)
* Backlinkg (Optional)
* Generated Graph of connection (like [Obsidian])
* Search - inspired by [pelican's][pelican-search]
* "Archetypes" or similar (inspired by [Hugo's][hugo-archtypes])

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
* [mbBooks]
    * A supersimple SSG in rust - checkout its feature set
* [Github Actions Workflows examples][gh-actions-wf-examples]
    * Check these out for a better understanding of github actions ci

> It turns out I have come up with the same solution as [Urubu]. Looking at their docs they came up with **Markdown content with Jinja2** that's then **rendered into a Jinja2 HTML template**.
