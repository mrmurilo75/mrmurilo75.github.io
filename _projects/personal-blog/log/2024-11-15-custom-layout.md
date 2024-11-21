---
title: Custom Layout
project: personal-blog
category: log
---
[resume]: {% link resume.html %}
[jekyll-themes-doc]: https://jekyllrb.com/docs/themes/
[jekyll-includes-docs]: https://jekyllrb.com/docs/includes/
[jekyll-layouts-docs]: https://jekyllrb.com/docs/layouts/


## Status



---

## Idea

I want to apply custom styling to the site, and have more control over looks and feel. I liked what I've done for the [resume], so I would like to apply something like that to the whole site.

In Jekyll this UI control would be called a [theme][jekyll-themes-doc]. But the docs on themes is lacking, in my opinion. It doesn't really says how to create a theme.

Since we are using the default theme *"minima"*, I have copied all files from it with `cp -r $(bundle info --path minima)/* .`. Then I evaluated the relevant files and reverted any overrides (like README.md) with git. 

> Warning! The `cp` command above will override conflicting files. Only do this on a clean working tree, so you can revert unwanted changes.

So, from this example, I found that it is basically composed of:

1. \_includes/ - These are html snippets (see [docs][jekyll-includes-docs]).
2. \_layouts/ - These are html templates (see [docs][jekyll-layouts-docs]).
3. \_sass/ - These are the styling files.
4. \assets/ - Any resource besides the above that be used, like an image for background.

### Reusable Pieces

The *\_includes* are reusable from .md as well, so these are a solution for reusable styled pieces. For customization of the piece we can pass in variables. If we want to have content inside a styled HTML block we could use opening and closing *includes*.

#### PBlock

To create a reusable container with a left and right (for big screen) like the [resume] we can create 3 pieces of *includes*:

1. PBlock-open: creates a new open tags for container and the left side
2. PBlock-break: closes the left side and opens the right side
3. PBlock-close: closes the left side and the container

> PBlock because its the **P**ink Block.

---

## Roadmap

For the moment, I will simply apply the color and minimal layout changes. Then the layouts need to be planned. I think that the reusable pieces will come from those. 

**Use a drawing software** to visualize the goal, before writing HTML/CSS. ~~I sometimes skip this and end up spend more time stupidly.~~

## Next

[ ] Make the border's in $on_palm **smaller** 

### [-] Minimal layout changes - based on [resume]

[X] Change background color to darker pink

[X] Put main content in a paper-like wrapper with content inside pink box

[ ] h1 inside a pink box, and other content in inner white box with border (use column, like mobile version of [resume])

> should be easy enough since h1 comes from title so its already applied by layout template

[X] Header with no background ~~in white box - all the way to the sides~~

[X] Footer  with no background ~~in white box - all the way to the sides~~

## To Be Planned

[ ] Create the PBlock reusable pieces - **See above in #PBlock**

[ ] Notebook and Projects listing pages

[ ] Projects index pages pieces

[ ] Inner Notebooks and listing

[ ] Project's logs

[ ] Project's discussions

[ ] Project's reports

## Done


---

## Notes

### Header links

I have found that the header links in *minima* are based on 2 criteria:

1. layout: page
2. title: *not empty*

