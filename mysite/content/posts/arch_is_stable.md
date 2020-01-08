---
title: "Arch is stable"
date: 2020-01-07T17:32:24+03:00
draft: false
showthedate: false
---

As you might notice after reading [the about me page](/../about), I have the macbook and don't run macos.
It's not a popular choice and folks around keep saying that macos is unix or unix-like system
and has everything you need including tools for development pursope. It's kinda true and most of the tools are available.
Despite of that I faced a number of issues with software not being able to compile for macos on macos.
I haven't tracked any of those issues and barely remember any them. You just have to believe me on that one. And for anyone wondering, yes, I can read readmes and follow the steps. I do know how to update software on macos and install missing packages or the right version of them. So I'm sure it wasn't a me problem.

Another reason of switching is that I've been following the development of [sway wm](https://swaywm.org/) for a whlie
and therefore had a desire on get my hands on this window manager and give [wayland](https://wayland.freedesktop.org/) a try.

The idea behind this post is to log issues that occured during my usage of the system. It's not a problem -- solution type of reading. The only thing you might get from this post is to see when I had bad days. The post has no date and is aimed to be updated on regular basis.

### 2020
- 01/08 Fonts don't load in tty. Can't start a sway session. Reboot helped
- 01/07 Brightness increase button doesn't work. Relaunch wayland session helped
### 2019
- 11/14 No voice during call via telegram
- 11/11 tty session killed itself after running pytest. (Alex's sugestion: the kernel wasn't fully loaded)
- 11/10 Zshrc config doesn't load. EDITOR variable problem
- 11/07 Sway tab with qutebrowser is inactive and there's no way to go there
- 11/06 Sound doesn't work (XDG_RUNTIME_DIR is unset in zshrc)
- 11/05 Sway doesn't launch (kernel update helped)
