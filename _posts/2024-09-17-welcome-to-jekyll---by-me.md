---
layout: post
title:  "Welcome to Jekyll! - By me 😁"
date:   2024-09-17 19:47:00 +0000
---

# Welcome to Jekyll!
This is not the default file created by Jekyll, but welcome to Jekyll! I'll teach myself (or anyone else that stumbles here) how to replicate the very first deployment of this site. Many of the information here might be replicated from source, but I've shot myself in the foot by relying on external information that can be changed, moved, or deleted. My default behaviour has been to take note and link the sources.

---

# Goals
The goal of this project, at the very start, was to have a place where I could put notes on the studies and projects I make. My first idea was to run a fully featured Django Wagtail blog, but since I got older and wiser I decided that deployment speed was key and that changes should be incremental. In most cases it is more important to do it than to do it perfectly, so I re-evaluated my needs.

One thing I was sure is that I would like it to be text-based. Unlike file formats like PDF, text files have been around long enough that it is safe to assume that they will be here until I leave this earth (or body, or consciousness - whichever comes last). This way I can move to another OS, software, or even print if needed. The information needs only the information. Since I want some structure, I figured that Markdown is the way to go. It is nice in text and can be further processed for styling, without the clutter of HTML.

Having decided that I only needed a text editor for the actual information, and knowing that I would definitely use git, I figured Github Pages would be a easy deploy. While searching for template repositories for this purpose, I stumbled upon Jekyll. It provides Markdown processing and it is well integrated with Github Pages, which makes it **very** easy to deploy. Also, since I am using Github Codespaces (I only had a Wndows machine at the time 🤢), setting it up was pretty easy - altough it wasn't in the docs.

# Step-by-step
### 1. Create a Github Repository.
If you want it to be your user's Page it has to be named `<username>.github.io`. Select the option to **create a README** so the repository is created, instead of requiring a push.
### 2. Create a **Codespace** for your repository.
### 3. Create a new Jekyll project
Once in the codespace, create a new jekyll project then move all content to the root folder (of the repo).
``` bash
$ jekyll new template
$ for f in $(ls -A) ; do mv template/$f ./$f ; done
```
### 4. Configured Github Pages to use Jekyll

![Github's Settings Page With Github Action Selected][2024-09-17-setup-github-pages-to-jekyll-action]

1. Go to the **Settings** tab in your repo's page in github. (On the left-most top corner)
2. Select the **Pages** nvaigation item. (On the left-side navigation panel)
3. Change the **Build and Deployment**'s **Source** option to **GitHub Actions**.
4. Click on the **Configure** button on the **GitHub Pages Jekyll** that appears.

This will take you to a **New File** page, where you can edit the default *.github/workflows/jekyll-gh-pages.yml*. Simply click to commit (at the top right corner), to add it to your repository.

[2024-09-17-setup-github-pages-to-jekyll-action]: /assets/img/posts/2024-09-17-welcome-to-jekyll---by-me/2024-09-17-setup-github-pages-to-jekyll-action.jpg
---

# Extra Content
## Adding Images to Jekyll
During the writing of this post there was the need to add the above image, on the section '**4. Configured Github Pages to use Jekyll**'. At first, my idea for the folder structure was `/assets/img/_posts/<post name>/<datestamp>-<image name>.<ext>`, (for example, the resulting path would be `/assets/img/_posts/2024-09-17-welcome-to-jekyll---by-me/2024-09-17-setup-github-pages-to-jekyll-action.jpg`). 

When running `jekyll serve` to see the site's progress, the following error occured:
```bash
    Error: could not read file /workspaces/mrmurilo75.github.io/images/_posts/2024-09-17-welcome-to-jekyll---by-me/2024-09-17-github-pages-setup.jpg: invalid byte sequence in UTF-8
```

Upon researching, I found an [github issue][jekyll-img-under-_post-issue] on the jekyll repo that seemed to describe the problem I was having. Jekyll processes the anything under `_posts` as a post, so it was trying to read the image as UTF8. The solution was to simply change the folder name to remove the `_`, resulting in `/assets/img/posts/<post name>/<datestamp>-<image name>.<ext>`.

[jekyll-img-under-_post-issue]: https://github.com/jekyll/jekyll/issues/2592
---

# References

* [Creating a GitHub Pages site with Jekylla | GitHub Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)
* [Jekyll Docs](https://jekyllrb.com/docs/)
* Some assistance from [ChatGPT](https://chatgpt.com/)!