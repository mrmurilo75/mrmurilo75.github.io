---
title: Permanently swap Caps and Escape
layout: post
---
[askUbuntu-switch-caps-esc]: https://askubuntu.com/questions/363346/how-to-permanently-switch-caps-lock-and-esc
[dconf configuration system]: https://wiki.gnome.org/Projects/dconf


Looking to swap caps and escape I found the following xkeyboard command:

```bash
$ setxkbmap -option "caps:swapescape"
```

However, this command only works during the session. If I logout, the session is closed and the keys are reset.

Upon further research I came across [this post][askUbuntu-switch-caps-esc], which mentions `dconf-editor`, the GUI editor for the [dconf configuration system].

## To configure a xkeyboard option

1. Install it with `sudo apt install dconf-editor`
2. Open `dconf-editor`
3. Navigate to *org >> gnome >> desktop >> input-sources*
4. Add the required option to 'xkb-options'. To swap caps and escape, add `"caps:swapescape"`.
