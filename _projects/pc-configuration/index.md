---
layout: page
title: PC Configuration
category: index
project: pc-config
---
[omakube]: https://omakub.org/
[ohmyzsh]: https://ohmyz.sh/
[ohmyzsh-docs]: https://github.com/ohmyzsh/ohmyzsh/wiki
[caps-swap-escape]: {% link _projects/pc-configuration/reports/2024-11-04-caps-swap-escape.md %}


## Exploration

- [ ] checkout [omakube] for a ready-made config.

### Terminal

- [ ] checkout [Oh My Zsh][ohmyzsh] for a pre-configured terminal
    - [ ] checkout [docs][ohmyzsh-docs] for relevant features

- [ ] tmux - checkout from negligent-octopus project notes

## To be Planned

* A pdf reader
* A note taking app with support for drawing tablet

Candidate: **Xournal++**

---

## Current Setup

### Navigation

#### Browser:

**Firefox**

##### Extensions:

###### Search:

* [Brave Search](https://addons.mozilla.org/en-US/firefox/addon/brave-search/)

###### Password Manager:

* [Bitwarden Password Manager](https://addons.mozilla.org/en-US/firefox/addon/bitwarden-password-manager/)

###### Ad Blocking:

* [Privacy Badger](https://addons.mozilla.org/en-US/firefox/addon/privacy-badger17/)
* [AdGuard AdBlocker](https://addons.mozilla.org/en-US/firefox/addon/adguard-adblocker/)
* [PopUpOFF - Popup and overlay blocker](https://addons.mozilla.org/en-US/firefox/addon/popupoff/)

###### Tab & Session Management

* [Tab Session Manager](https://addons.mozilla.org/en-US/firefox/addon/tab-session-manager/)
* [Tree Style Tab](https://addons.mozilla.org/en-US/firefox/addon/tree-style-tab/)

### Development

**Github CodeSpaces**

#### Plugin (project independent)

* [Vim by vscodevim](https://marketplace.visualstudio.com/items?itemName=vscodevim.Vim)
* [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

### Terminal

**bash** (Pop!OS built-in)

#### Additional packages:

##### APT

* [silversearch-ag](https://github.com/ggreer/the_silver_searcher)
* tmux
* nvim

> These will be elaborated when in-use for development.

### Configuration

#### Keyboard

* Use **English (Canada)**
* Swap CAPS with ESC - [see more][caps-swap-escape]

---

### Discussions

{% assign discussions = site.projects | where: "project", page.project | where: "category", "discussion" %}

#### Open

{% assign is_open = discussions | where: "open", true %}
{% for discussion in is_open %}
* [{{discussion.title}}]({{discussion.url}})
{% endfor %}

#### Closed

{% assign closed = discussions | where: "open", false %}
{% for discussion in closed %}
* [{{discussion.title}}]({{discussion.url}})
{% endfor %}

---

## Monitoring

### Logs

{% assign logs = site.projects | where: "project", page.project | where: "category", "log" %}
{% for log in logs %}
* [{{ log.date | date: "%Y-%m-%d" }} {{log.title}}]({{log.url}})
{% endfor %}

---

## Review

### Reports

{% assign reports = site.projects | where: "project", page.project | where: "category", "report" %}
{% for report in reports %}
* [{{ report.date | date: "%Y-%m-%d" }} \| {{report.title}}]({{report.url}})
{% endfor %}
