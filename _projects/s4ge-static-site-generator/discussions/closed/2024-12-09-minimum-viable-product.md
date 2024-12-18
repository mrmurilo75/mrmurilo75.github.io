---
title: Minimum Viable Product
category: discussion
project: s4ge
date: 2024-12-15
open: false
---
[project-index]: {% link _projects/s4ge-static-site-generator/index.md %}
[related-log]: {% link _projects/s4ge-static-site-generator/logs/2024-12-09-mvp.md %}
[urubu-html-on-md]: https://urubu.jandecaluwe.com/manual/templating-in-pages.html


## Conclusion

> This discussion is closed in favor of a more granular approach. See the [project index][project-index].

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

#### Noted:

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

- [configuration files][see Configuration Discussion below]
- http server for development

#### Configuration Discussion replicated here:

I think that the configuration in Jekyll is not great, especially the collections and the defaults. I think I have a better solution.

First and foremost, anything that can be defined in the front-matter can also be defined in the configuration files.

**Each folder is configurable with a `_config.yml`.** Using a specificity override - like in html/css, where **the most specific is used**.

**Front-matter would be the most specific**, and override any others. Then the folder confgiuration, then the parent folder configuration, and so on. At the project root are project configuration.

**Configuration options will be added as needed.**

---

### 2024-12-09

The expectation to jump from POC to an MVP with all these features was waaaaayy too high. So let's reevaluate expectations and priorities.

First of all, the goal of this project is not to be another open source static site generator to be used by the masses. **It's a personal project to be a file-based CMS** - and generate my own static site.

What is *my* workflow?
    1. Front-matter in md
        `-> 2. Template construct in md (with front-matter context)
            `-> 3. Render md to html
                `-> 4. Render template to site
                    `-> 5. Copy remaining resources

At the moment of writing this, this has been implemented using result files between each step. This is obviously not feasible, even for my own site. It takes a huge amount of files to fully render.

What has been done wrong?

1. Too many features to implement (no focus)
2. Too dependent on an unknown tool (`doit`)

What's next?

1. Let's make this more granular.

Discussions don't need to be on a whole version. Maybe a feature, maybe an architectural decision. It has it place but much of the time trying to think ahead - specially in a type of project I don't have experience in - is like trying to see the future.

Moreover, the POC was too small. The POC should be where the project is now! It has the minimal workflow using a given tool, and it is enough to give insight into how this all has to actually work. I *now* have enough information to plan something out and know scope of the project (file-based CMS).

2. As spoken on [POC], I thought a static site would be a build process, and planned to build on top of the `doit` tool. But although that is *kind of* right, building a site has a lot more piping content and context than the build tool is made to handle - at least as far as I know it.

One big mistake I made was using the tool before I even knew how to use the tool. Then mistakes happen and I don't know why. This project my itself has a lot of things that could go wrong, and that gets a lot worse if I am using a tool that I don't really understand.

Besides this tool I realised that I haven't messed with Python's file manipulation in a very long while. Since this project is about building something with python from wht ground up, without any framework for the actual features, I need to actually know it - just googling doesnt cut!

What was done right?

1. One side effect of using doit the way I did is that the implementation was made granular! Beacuse every task would do one thing in its scope and then and only then, another task would grab the result from the file system.
