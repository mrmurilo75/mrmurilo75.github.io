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

---

## Applying keyboard layout to VS Code in Browser

My current setup is based on Github Codespaces in the browser, which means VS Code. For some reason, they decided that the keyboard layout is specific to VS Code, not the same as the browser window or the system. This means they override what gets sent to the file, but the key is pressed at a system level. The result is that pressing CapsLock with the above swap will do nothing, but pressing Escape key will activate CapsLock AND send an ESC key to VS Code.

The solution for this is to override the default so that VS Code listen to the system's key binding. 

1. At the top bar, search for VS Code's `settings.json` (User preferences)
2. Add the following:

```json
{
    "keyboard.dispatch": "keyCode"
}
```
