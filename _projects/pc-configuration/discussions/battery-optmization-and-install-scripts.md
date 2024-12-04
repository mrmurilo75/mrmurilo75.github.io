---
layout: page
title: Battery Optmization & Install Scripts
category: discussion
project: pc-config
---
[omakube]: https://omakub.org/
[maximizing linux battery life]: https://thelinuxcode.com/15-tips-improve-laptop-battery-life/
[reddit linux battery]: https://www.reddit.com/r/linux4noobs/comments/zdjqc9/battery_life_on_linux_sucks_out_of_the_box_i_got/
[github-jcchikkikomori-matebook-d15]: https://github.com/jcchikikomori/linux-on-huawei-matebook-d15-2021/tree/master


This project is the monitoring and tracking of changes and investigations I make while tweaking my personal setup.

I am a fan of Unix and Unix-like systems. I like changing OS not only because I can try new work flows but because I am a cleaning freak, even when it comes to my systems. Said that, I need an easy and realiable process to have my system up and running as fast as possible.

## Current State

I am currently using a Huawei Laptop - the Matebook D15. I already found that battery life is a common issues, as well as some missing drivers. I could not find the sound card drivers anywhere, but since I use bluetooth headphones, I am not too worried.

I have found [this github repo][github-jcchikkikomori-matebook-d15] for this exact model, that tracks relevant information and contains some util scripts.

## Planned work

[-] Investigate battery optmizations
* See this article on [maximizing linux battery life]
* And this [reddit post][reddit linux battery]

[X] Swap esc:caps at logon
* DONE: [See details][caps-swap-escape]

### Sub-Project

[ ] Configure development environment - Create dependencies install scripts (look at [omakube] and [bin-setup] for reference)
