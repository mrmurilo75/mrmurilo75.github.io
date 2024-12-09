---
title: Minimum Viable Product
category: discussion
project: s4ge
date: 2024-12-09
open: true
---
[related-log]: {% link _projects/s4ge-static-site-generator/logs/2024-12-09-mvp.md %}
[urubu-html-on-md]: https://urubu.jandecaluwe.com/manual/templating-in-pages.html
[discussion-configuration]: {% link _projects/s4ge-static-site-generator %}


## Conclusion

> To track implementation check out [the related log][related-log].

First of all, we'll need to make the POC more robust to be an actual product. It is currently using only one file just as an example of the usage of the selected technologies. To extend this we'll need to implement some more features.

- [ ] **Recursively** render md in inner folders
- [ ] Apply **selected** templates
- [ ] Rebuild upon change - a standard feature of doit

After this first improvement, the aim of the MVP is to be compatible with **jekyll content** for an easy migration. This is not accounting for the blogging-related features, although those will be extensions in the future.

- [ ] Templating constructs in md
- [ ] **Front-matter** configuration and user variables
    - layout
    - title, dates, ...

The **acceptance criteria** for this version is to **use it for my own personal site**!

Some topics have been set to be discussed in the future:

- [configuration files][discussion-configuration]
- http server for development

---

**2024-12-09**

First of all, we'll need to make the POC more robust to be an actual product. It is currently using only one file just as an example of the usage of the selected technologies. To extend this we'll need to implement some more features.

- [ ] **Recursively** render md in inner folders
- [ ] Apply **selected** templates
- [ ] Rebuild upon change - a standard feature of doit

After this first improvement, the aim of the MVP is to be compatible with **jekyll content** for an easy migration. This is not accounting for the blogging-related features, although those will be extensions in the future.

- [ ] Templating constructs on md
- [ ] **Front-matter** configuration and user variables
    - layout
    - title, dates, ...

The **acceptance criteria** for this version is to **use it for my own personal site**!

Some topics have been set to be discussed in the future:

- [configuration files][discussion-configuration]
- http server for development
