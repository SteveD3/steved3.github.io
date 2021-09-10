---
layout: default
categories: phishing
title: KeyBank phishing attack hits Spectrum users too
date: 2021-09-10
description: A phishing attack targeting KeyBank users also attempts to snag Spectrum accounts.
image: /images/phish-img.jpg
---
## KeyBank challenge questions
I received an interesting phishing email Wednesday (08-September-2021).

The message claimed to be from KeyBank. The original encoded message, as it first appeared in my inbox, is below. The encoding likely helped the lure[^2] bypass email filtering.

Now, I'm not a KeyBank customer. So the email immediately came across to me as a scam when I looked at the from field. The body of the message confirmed my logic. All of my email arrives in plain text, as it allows scams like this one to standout more easily. The use of the Greek letter in the word _'Bank'_ is another telltale sign that something is off.

### Encoded

![An encoded KeyBank phishing email, which avoided spam filtering.][img1]

Once HTML was enabled, and the full message was decoded and rendered, the idea that this was a scam really hits home. The font, the message spacing and wording, the usage of an incorrect date, the link that uses Twitter's shortened URL service. All of these things combined scream phishing attack. So I did what any other researcher would do, I set off to see if I could acquire the phishing kit itself.

`(Spoiler: I did get the phishing kit's source code.)`

### Decoded

![The decoded KeyBank phishing email, which avoided spam filtering.][img2]

## Captcha for everyone

The moment that the landing page [^1] is loaded, the victim is presented with a Captcha prompt, and the KeyBank logo. In all there are twelve steps, and the goal is to collect usernames and passwords for KeyBank and Spectrum customers, as well as several bits of personal and financial information.

The KeyBank aspect of the phishing attack aims at login details, as well as security questions (see the image at the end of this post), Social Security Number, and phone number. Once that is done, the scam moves on to the Spectrum element, which collects the victim's username and password, as well as their full name, address, date of birth, credit card information, and Social Security Number.

## Return of an old name

Digging into the source code for this phishing kit, the first thing I came across is the personal brand for `Cazanova Haxor` who is a well-known phishing kit developer. I've written about him at work, and [other researchers](https://www.wmcglobal.com/blog/cazanova-phisher-steals-from-himself) have [covered his scams extensively](https://www.wmcglobal.com/blog/cazanova-morphine-kit-deep-dive).

## Platform development

Another interesting aspect to the code used for this phishing attack, is that it leverages a popular PHP framework, called CodeIgniter. As the [project's website](https://codeigniter.com/) explains:

>"CodeIgniter is a powerful PHP framework with a very small footprint, built for developers who need a simple and elegant toolkit to create full-featured web applications."

The CodeIgniter platform made the phishing kit's source code easy to navigate and index for [Kit Hunter](https://steved3.io/data/Kit-Hunter-2.0-Getting-Started/2021/09/07/), but it also feels like `Cazanova Haxor` used it for it's modular features, as well as some of the built-in security mechanics, which protect it from common attacks like Cross-Site Scripting (XSS), and Cross-Site Request Forgery (CSRF).

## Dead scams

This scam was dead the moment it hit my inbox. As of now, the URL fails to load properly, and [the domain itself is flagged as malicious](https://urlscan.io/result/61042c25-44d0-4b31-8aa9-79dc1cfd476b/#summary) in most browsers. Once reported, it didn't last long at all. But the lesson here is that you should trust your gut. If something feels like it's wrong, then it is. There were plenty of red flags in this attempt, the least of which was that I'm not a KeyBank customer.

![There were 12 steps required for this phishing attack.][img3]

---

[^1]: A landing page is what is displayed when a victim accesses (clicks) the phishing link within a lure.

[^2]: A lure is what entices the victim into accessing the included phishing link. Often this can be an alarming message sent via email or SMS, or a post on social media. The key is that the criminal has created a sense of urgency, alarm, or curiosity in the victim, thus getting them to commit to accessing the link.



[img1]:https://steved3.io/images/posts/keybank-1.jpg
[img2]:https://steved3.io/images/posts/keybank-2.jpg
[img3]:https://steved3.io/images/posts/KeyBank-3.jpg
