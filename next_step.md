---
layout: page
title: The Very Next Step
permalink: /next-step/
---

## Goals

This site is a hub of knowledge for myself. Not only will I write studies/posts, but I plan on having most - if not all - the information that can be shared in here. It might be too ambitious, but we should always **strive for greatness**. In light of this objective, I'll keep this page as a tracker for the next change to be made to this site.

--- 

### Jekyll Theme and Sections

I want this site to have a better structure. I've seen Jekyll [themes that have multiple tabs][theme-al-folio], even with dropdowns. I plan on replicating such functions, but first I need to plan out how that is going to be done. Here's the planned sections so far:

1. **Posts**: I want the blog posts to be, by default, finished articles/studies related to technology and software.
2. **Zettel**: I'll likely implement over time a simple zettelkasten-like structure, and give it it's own section. 
    I'll still write a section on the home page and a post talking about [zettelkasten][zettelkasten]. 
3. **Projects**: A projects section to keep track of development of ongoing projects and plan future ones.
4. **Hobbies? Life?** I want to have my reflection anything unrelated as well. Besides the zettelkasten (which would encompass it all), I would like to have finished essays as well and maybe reports on real-life adventures.

[theme-al-folio]: https://alshedivat.github.io/al-folio/
[zettelkasten]: https://zettelkasten.de/

---

### Distilled Action

I realise the above is a bit too much for only one task. It is not a task, but a project within the wider project that is this site (I haven't figured terminology for it yet). Here's the planned next steps:
1. Finish up reading the [Jekyll Docs](https://jekyllrb.com/docs/)
2. Write up ideas and relevant informations
3. Plan next actions based on new information

Guardrail: I dispersed myself on thinking about layout, but that is not the focus here. We'll first have simple pages working with listings from collections.
Thoughts so far:
    It seems the best way to go about this really is collections. They can have a permalink attribute to get the date from the filename or the front matter date key (preferably because it then orders by date).
    Zettel needs only a few entry points, but those can be a tag on the collection.
    As per the life or hobbies, those will be in the zettel. We can make post off of those, and create a separate collection if necessary (there are also other mechanisms to filter that can be evaluated later on).
Guardrail: I don't know enough about what I'm trying to build to foresee issues or plan improvements. Trying to do so will only limit myself and possibly create more issues than it solves - it might then be classified as *overengineering*. **Keep focus. Fix as needed. Improve when opportune.** 

---

## Tracker

Here's a short progress report:

| Date | Short description |
|------|-------------------|
| IDK | Create Jekyll Project and Deploy |
| IDK | Write [first post][welcome-to-jekyll] |
| 2024-09-18 | Create [this page]({{ page.url }}) |
| 2024-09-23 | Annotate on [this page]({{ page.url }}) |
| 2024-10-02 | Add new [page for note](/some-things-to-keep-in-mind/) |
| 2024-10-06 | Add [notes](/some-things-to-keep-in-mind/) |

[welcome-to-jekyll]: {% post_url 2024-09-17-welcome-to-jekyll---by-me %}