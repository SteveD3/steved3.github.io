---
layout: post
categories: [code, phishing]
title: Quick Update About Kit Hunter
date: 2021-01-03
description: Now that 2020 is over, and 2021 is official, I wanted to post an update on Kit Hunter.
---

### Kit Hunter v1.0

In November, I updated [Kit Hunter to version 1.0](https://github.com/SteveD3/kit_hunter "Link to Kit Hunter version 1.0") after extensive testing, making sure it finally works on Python 3. For those not familiar, Kit Hunter started as a way for me to learn Python development, and it sort of took on a life of its own from there. Phishing has always been a topic that I've enjoyed researching, and so Kit Hunter was a way to learn something and focus on one of my interests.

The tool itself is for server administrators, but researchers might get some use out of it as well. A friend recently described it as a scripted version of [Grep](https://linuxcommand.org/lc3_man_pages/grep1.html "Grep searches standard input or files for matches of a given pattern."). While that is true, the core element is one of context.

For now, the easiest way to describe Kit Hunter is the script's Read Me on GitHub:

>Kit Hunter is a basic scanning tool that will search directories and locate phishing kits based on established markers. As detection happens, a report is generated for administrators.

It's one thing to tell administrators that phishing kits need to be detected and removed quickly, but it's another thing entirely to provide a tool that assists with this process. That's what Kit Hunter is for. As this website grows, the plan is to expand on that overview with detailed posts concerning the mechanics of the script itself, and the elements that go into detecting phishing kits on your servers. I'll also explore use cases for the script.

### Kit Hunter v2.0

Development on version 2.0 of Kit Hunter is ongoing. One thing I'm excited about is the ability to search within archives (.zip, .rar, .tar, .gz) using the same scanning techniques needed when searching directories and files. Also, the speed of the scanning has greatly improved.

For example:

>4,816 items scanned.
>Kit_Hunter V1 processed all files in 00h : 11m : 52.20s
>Kit_Hunter V2 processed all files in 00h : 00m : 56.38s

Expect more updates soon.
