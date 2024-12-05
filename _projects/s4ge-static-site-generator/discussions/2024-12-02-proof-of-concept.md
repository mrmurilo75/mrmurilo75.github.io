---
title: Proof Of Concept
category: discussion
project: s4ge
date: 2024-12-02
open: true
---
[Urubu]: https://urubu.jandecaluwe.com/
[yaml-intro]: https://www.yaml.info/learn/index.html
[usetinycms]: https://usetinycms.com/
[Make]: https://www.gnu.org/software/make/
[doit]: https://pydoit.org/
[gh-actions-jekyll-run]: https://github.com/mrmurilo75/mrmurilo75.github.io/actions/runs/12022286759/workflow
[mistletoe]: https://github.com/miyuchina/mistletoe
[commonmark-implementations]: https://github.com/commonmark/commonmark-spec/wiki/list-of-commonmark-implementations
[Jinja2]: https://jinja.palletsprojects.com/en/stable/
[related-log]: {% link _projects/s4ge-static-site-generator/logs/2024-12-03-version-0.1.0.md %}


## Conclusion

> To track implementation check out [the related log][related-log].

Run a **build process** on a source, producing an output. Therefore the best tool for the job is **build tool**, like [Make]. However, since we want to keep things in the Python world we'll use **[doit]**.

### Target Workflow - for version 0.1.0

For the moment being we'll focus on a simplified workflow.

1. Source in **pure markdown**.
2. Templates in Jinja2.
3. No extra context (config or data file).

Source material is placed in the `_source/` folder. Filetypes other than '.md' are simply replicated in destination. Because of this, links can use the relative path or the root as the source directory. In case of '.md' files, the extensions is replaced with '.html'.

For example, if you have:
```bash
_source/
    ├── index.md
    └── images/
        └── herbs.png
_templates/...
```

You could add the image in `index.md` by adding:

```markdown
...
![Herbs on fire](/images/herbs.png)
...
```

The default output folder is `_site/`. This makes it compatible with existing [Github Actions template for Jekyll][gh-actions-jekyll-run]. The only step that requires override is 'Build with Jekyll' to our own build command.

Given the above example, the result after build would be:
```bash
_source/
    ├── index.md
    └── images/
        └── herbs.png
_site/
    ├── index.html
    └── images/
        └── herbs.png
_templates/...
```

### Known Limitations

Given this setup, anything beyond pure markdown is required to be implemented directly in the templates.

### Tools

#### Build Tools

* **[doit]**

#### Markdown Processor

* **[mistletoe]**

> Since this is planned to be configurable, it could be any the [commonmark implementations][commonmark-implementations]. Mistletoe was chosen for its rendering options, which could be a config option.

#### Templating Engine

* **[Jinja2]**

---

**2024-12-05**

> Rename to Proof Of Concept

**2024-12-03**

> See conclusion above

---

**2024-12-02**

## Inspirations

* [Urubu]
* MVC / MVT Architecture
* Jekyll uses - like [al-folio]
* Use-cases:
    * [My personal site][personal-blog]
    * A portifolio / resume site (like [my lovely designer's][loi-portifolio-figma])
    * A customized static site generator (you upload source material, like images and markdown, into a configured instance and it spits out a site applying templates)
* [usetinycms]
    * What we are trying to acomplish is somewhat the "engine" behind this. Except for the writting and the sql (which in our case is the file system), what we are trying to acomplish is the same. We could on top of this build system, have a wysiwyg web-based editor, and have a CI/CD implemented when a user "publishes" a script, which means writing for a buffer structure into the file.
    * The problem with this is that the "fields" (like main content, title, etc are pre-configured). The pure markdown cannot link to another article without hard linking of live. Advanced function, like listing all post linked to an author, are only doable if pre-implemented or using a templating engine, like Jekyl uses Liquid and extends it.

> It turns out I have come up with the same solution as [Urubu]. Looking at their docs they came up with **Markdown content with Jinja2** that's then **rendered into a Jinja2 HTML template**.

### The hard part

What I'm struggling with the most is figuring out how to connect things in source. Like in my own site, I want to list project's which are a subdirectory.

### The simplest setup

Would be for a personal site like my own. Add source markdown with Jinja2 that requires context on the file structure.

So theres a pre-process context gathering, then render Jinja2 markdown, then render HTML from configured Jinja2 templates.


## Implementation

**version 0.1.0**:

* source in `_source/` written in markdown with Jinja2
* midway markdown in `_prerender/`
* final render applying templates in `_output/`

**Which templates to apply for final rendering?**

Replicate the file structure in `_config.yml` to define templates in a cascading matter.

---

* **Filepath-based configuration**

As **routes in a static site** are based on the **filepath** requested, it makes sense that the configuration be based on filepath as well. We'll go a step further and think of as **cascading**.

The root of a folder can have a file `_config.yml` that defines


As it makes sense for a static site, routing is file based. Therefore, it makes sense that the configuration is based on the file structure!

Key words at the leaf will actually determine the configuration. Multiple files formats can be used for the configuration, but for me its easier to think of json.

Start with a mapping

```json
{
    "_config": {
        "_source": "_source/",
        "_destination": ".",
        "_process": "_process/",
    },
    "_source": {
        "_apply": {
            "apply_jinja2": [""]
    }
}
```

---

Underscoring is a way to reserve words in the configuration. Avoid underscoring filenames.

> I mean "underscoring" as adding an underscore to the beginning, like "_source".

The configuration is based on the folder structure

the root level applies to the root level of the source folder

Definition:

_source by default is _source/

_destination by default is the project root

_process is by default _process/

each entry in config will try to be matched in the folder structure

define the processes by listing them

For more yaml info checkout [this introduction][yaml-intro]

---

Scope:

* Gather **context**: Configuration, File structure, file information
* Apply processes

Ideas:

Be as light-weight as possible, with minimal development environment. Have focus on results.

1. Gather config in yaml (if even empty)
2. Gather file structure
3. Apply Jinja2 to files
4. Apply Markdown to results
5. Apply Jinja2 to generate final result
6. ~~Copy remaining~~

> Source to be processed is kept in dedicated folder (`_source/`), and results are placed at root (by default). This way unprocessed files are untouched.

The basic structure for a project is:

```bash
_source/
_templates/
_config.yml

# everything else
```
