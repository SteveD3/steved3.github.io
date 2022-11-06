---
layout: default
categories: phishing
title: Hybrid phishing kits and TodayZoo
date: 2021-10-21
description: Recent research shows that criminals are still jacking code to create hybrid phishing kits
image: /images/stock/phishing_email_icon_abstract.jpg
---

Over the years, criminals have constantly lived up to the saying that there is no honor among thieves. They're criminals, so it isn't like we, the defenders, expect anything less.

However, [research from Microsoft](https://www.microsoft.com/security/blog/2021/10/21/franken-phish-todayzoo-built-from-other-phishing-kits/), where they explore a hybrid phishing kit called TodayZoo, recently caught my attention. It's a solid example of crooks stealing from crooks.

As a bonus, for me at least, when I got to the end of the Microsoft article, I noticed they were citing my research ([a Kit Hunter blog post](https://web.archive.org/web/20211021153139/https://www.microsoft.com/security/blog/2021/10/21/franken-phish-todayzoo-built-from-other-phishing-kits/)) in their work. Really cool. Ego tripping aside, it was this remark from Microsoft that got me to thinking:

>A phishing kit built using pieces of code copied from other kits, some available for sale through publicly accessible scam sellers or are reused and repackaged by other kit resellers, provides rich insight into the state of the economy that drives phishing and email threats today...
>
>... Our prior research on phishing kits told us TodayZoo contained large pieces of code copied from widely circulated ones. The copied code segments even have the comment markers, dead links, and other holdovers from the previous kits.

## Criminals are going to crime

I've spent years studying the phishing ecosystem, from economics, to kit development, and everything in-between. In this time, there is one constant when it comes to the code in phishing kits. If it works, someone is going to steal it.

It is common to see recycled code, cracked registration systems, and hijacked development, because criminals don't like reinventing the wheel if they don't have to. So when I read Microsoft's report on TodayZoo, everything they said completely aligned with the things I've seen over the years.

Criminal phishing kit developers view code in much the same way that legitimate, non-criminal developers do. In their mind, code is code. If it helps get the task done, then it's worth using.

But unlike legitimate, non-criminal developers who use code snippets or open source elements in their projects, phishing kit developers have nothing but malicious intent behind their actions. After all, their endgame is crime.

Sometimes criminals jack code as a way to one-up or taunt a rival developer. Other times, the code is taken because it was easier to copy and paste in order to get the desired results. It's amusing to see comments in phishing kits about "respecting coders" and other anti-piracy notices, as if they do any good.

The interesting thing about the TodayZoo phishing kits, is that it appears the code recycling is more about functionality than ripping and jacking a rival's code.

## Some final thoughts

Now, [as far as Kit Hunter is concerned](https://steved3.io/khdocs/), it's been able to detect the kits that makeup TodayZoo since release. So if TodayZoo landed on a server that was using Kit Hunter for visibility, those kit elements would have been detected. New detection indicators are added regularly to the [GitHub](https://github.com/SteveD3/kit_hunter), so visibility and contextual awareness is only going to expand. However, I will be updating the detection rules to flag some of the indicators released by Microsoft.

But it was these existing detections that made me realize the recycled code was more functional than anything.

As Microsoft explained, there are at least five different kits being used to create TodayZoo projects, and each of those phishing kits have overlapping elements that copied in order to balance the hybrid kit. Many of these elements focus on obfuscation, exfiltration, and design mechanics that dictate the look and feel of the landing page. But here is the catch, these jacked code segments are easily tracked.

The [Microsoft post is well worth a read](https://www.microsoft.com/security/blog/2021/10/21/franken-phish-todayzoo-built-from-other-phishing-kits/) if you've got a moment. It's an interesting look at the topic of recycling in the phishing ecosystem.
