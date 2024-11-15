---
title: Custom Layout
project: personal-blog
category: log
---
[jekyll-themes-doc]: https://jekyllrb.com/docs/themes/


## Status

Evaluate and plan.

---

## Idea

Create a custom layout/templates. In Jekyll, these are the **Theme** - see [documentation][jekyll-themes-doc].

Since we are using the default layout *"minma"*, I havev copied all files from it with `cp -r $(bundle info --path minima)/* .`. Then I evaluated the relevant files and reverted any overrides (like README.md).

**Next step:** Override the layouts.