---
title: "Framework Migration"
project: personal-blog
category: discussion
open: true
---
[Lektor]: https://www.getlektor.com/
[Nikola]: https://getnikola.com/
[Pelican]: https://getpelican.com/
[Urubu]: http://urubu.jandecaluwe.com/
[lektor-demo-yt]: https://www.youtube.com/watch?v=lTWTCwuPdrU
[lektor-plugins]: https://www.getlektor.com/plugins/
[reStructuredText-nikola]: https://getnikola.com/quickstart.html
[reStrcturedText-official-reference]: https://docutils.sourceforge.io/docs/user/rst/quickref.html


## Conclusion


---

## Notes

**2024-11-18**

Since my main stack is Python, it would probebly be a good idea to change this blog's stack into Python as well. 

With the help of GePpeTto, I have narrow it down to:

* [Lektor]
* [Nikola]
* [Pelican]
* [Urubu]

### Reasons to change

1. Use known technologies, like Jinja2 for templates.
2. Customization and extendability - I might want to build something on top of it.
3. Contribution to open-source.
4. Read, learn, reference design and structure. Not just the code, but how are the decision made in open-source.

### Comparison:

* All of these use Jinja2 as the template engine. :)
* All support Markdown. They use different strategies to get this, but most use a third-party lib. 

> All of these can use reStructuredText (but I Nikola [pushes it][reStructuredText-nikola]) which seems more capable and just as easy. See more at [reStrcturedText official reference][reStrcturedText-official-reference].

2. Extendability:

Lektor: too much

* Has the most features, including an admin interface, and can have multiple "fields". See [this demonstration][lektor-demo-yt].
* This also means it's a lot more complex, if I want to extend it or participate.
* From [plugin][lektor-plugins] we can see what it cannot do, and also get some idea of useful features.
* All in all, too big and out of the scope. Their different file format is a deal breaker because it means being software locked.

Nikola: too old

* Pretty long lived project: more than 10 years. Pretty **complex** and sometimes **old code**.
* It also makes unecessary use of commands like `nikola new_post` which is not good imo.

Pelican: great! 

* This is a pertty robust project! It seems to have all the features and be well mantained. 
* They use pip for plugin, nad it seems their separations of concerns is pretty tight. 
* It will likely have extended support and solution finding, due to the projects size. 
* The only down side of all this is I might not be able to contribute!

Urubu: can I use it?

* This is a tiny project. 
* Unlike the others, which were blog-focused, it is a *micro CMS*.
* I can build on top of it! But the license is Copyleft :c

MyOwnSolution:

* I could build my own solution (mostly based on Urubu), to be a micro CMS.
* I would learn and practice some nice stuff like a mini-https server for local development.
* I probably only need to do what I want, most might be glueing pieces together by using third-party solutions like Jinja2.
* Downside: This will take a lot of time. I cannot wait for it to be developed to move the site. I could use Urub for now, since its the simpleset and probably most replicable set of features.

