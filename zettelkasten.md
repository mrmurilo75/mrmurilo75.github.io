---
layout: page
title: Zettelkasten
permalink: /zettelkasten/
---
[Obsidian]: https://obsidian.md/
[zettelkasten.de]: https://zettelkasten.de/
[intro-to-zettelkasten]: https://zettelkasten.de/introduction/

## Welcome to Zettelkasten

I first came in contact with the word *zettelkasten* while looking at the configuration of [Obsidian] (a markdown-based WYSIWYG editor). As the curious person that I am, I took this new word to Google and ended up in [zettelkasten.de]. This site is dedicated to the Zettelkasten Method, which in the words of the author can be described as:

> A Zettelkasten is a personal tool for thinking and writing. It has hypertextual features to make a web of thought possible. The difference to other systems is that you create a web of thoughts instead of notes of arbitrary size and form, and emphasize connection, not a collection.

If you are interested in this method, I recommend reading the [introduction][intro-to-zettelkasten].

---

## Entry Points

{% assign entries = site.zettelkasten | where: "entry", true %}
{% for entry in entries %}
* [{{entry.title}}]({{entry.url}})
{% endfor %}