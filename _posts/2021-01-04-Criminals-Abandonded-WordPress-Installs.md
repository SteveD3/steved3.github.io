---
layout: default
categories: phishing
title: A look at abandoned WordPress installs
date: 2021-01-04
description: Criminals love taking advantage of abandoned WordPress installations, often targeting vulnerable add-on scripts or modules, in order to upload phishing kits.
image: /images/phish-img-2.jpg
---

### Criminals love abandoned WordPress installations

Criminals love taking advantage of abandoned WordPress installations, often targeting vulnerable add-on scripts or modules to compromise the domain. They do this in order to upload phishing kits and other malicious payloads, and leverage the otherwise clean - or presumed safe - reputation of the compromised website. The older a domain is, the more valuable it can be. For this post, we're going to examine a website that has appeared in my daily phishing scans each day since November 12, 2020.

One of ten wards in the city of Saitama, in Saitama Prefecture, Japan, Iwatsuki is known as the City of Dolls due to its historical notoriety dating back to the 17th century. It isn't too big of a city, but it does have at least one fan. During my daily scans for phishing kits, I discovered one WordPress-driven website dedicated to reviewing love hotels in Iwatsuki.

The website appears abandoned, as the content has remained static for months, after being uploaded sometime in 2016 or 2017. Oddly, the WordPress installation has been somewhat maintained, or at least it is reporting that it's part of the 5.x release cycle (5.0.11). Yet, the facts are rather straightforward. Someone other than the website's owner has taken an interest in Iwatsuki and its hotels, or at least the websites' previously spotless reputation.

>A quick note: The website is still live, so I won't be naming or linking to it here. It's flagged by Google Safe Browsing, and doesn't appear in the fist 10 pages of common keyword searches.

### Basic email phishing

The image below is what the phishing kit's landing page[^1] on the compromised Iwatsuki website looks like.

![The hotel review website is still hosting an active phishing kit targeting email addresses][img1]

It's one of the more basic phishing kits circulating on the web. The lure[^2] used with these kits is usually something that warns the victim that their mailbox is about to be deleted unless they verify their email password. When the landing page is loaded, the script starts a visible clock at 01:15:09 which will countdown until zero. Once the user enters their password, the details collected are emailed off to the criminal listed in the `post.php` script.

### Good News and Bad News

There is some good news about this kit. Good News: It doesn't work. In the code for `loader.php`, the meta refresh callout is looking for a file that doesn't exist, resulting in a 404 page. It's possible this might alert the victim that something is wrong, assuming that the generic look and feel of the website itself wasn't enough of a warning already.

```php
<meta http-equiv="REFRESH" content="10; success.php?rand=13InboxLightaspxn.1774256418&fid.4.1252899642&fid=1&fav.1&rand.13InboxLight.aspxn.1774256418&fid.1252899642&fid.1&fav.1&email=<?php echo $_GET['email']; ?>&.rand=13InboxLight.aspx?n=1774256418&fid=4#n=1252899642&fid=1&fav=1">
```

>In the code above, `success.php` is missing, which is what triggered the 404.
>
>Also, notice the $email variable in the URL. When the victim submits the verification form, their email address is included, and sent along with the matching password. When the lure is sent to the victim, the link that is clicked includes the victim's email address, so it is collected automatically.

However, the bad news is that by the time the 404 page renders, the emailed credentials have already been shipped off. The `loader.php` file is supposed to trigger a chain that seeks additional verification from the user, which enables the criminals to get two copies of the victim's credentials.

Why would they do this? There a couple of reasons that come to mind:

1. The victim might enter the exact password they previously entered, thus offering confirmation to the criminal.

2. They will enter a new password, which gives the criminals a second password for their collection.

### Maybe it isn't a compromised domain

While the assumption is that this is a compromised domain, it is possible that the criminals developed this website on their own. Criminals are a clever bunch, and will go to great lengths to obfuscate their attacks. Designing a somewhat random website and leaving it harmless for a period of time isn't unheard of, and has certainly been done before. But, given the nature of the phishing kit, it's likely this domain was compromised, patched by the owner at some point, and then abandoned.

Either way, Iwatsuki domain and phishing kit continues to show up in my daily scans (as of Jan 6 2021). Attempts to reach the host and website owner have all failed. Sadly, there are a lot of other websites like this online, operating in the same situation; compromised and abandoned.

---

[^1]: A landing page is what is displayed when a victim accesses (clicks) the phishing link within a lure.

[^2]: A lure is what entices the victim into accessing the included phishing link. Often this can be an alarming message sent via email or SMS, or a post on social media. The key is that the criminal has created a sense of urgency, alarm, or curiosity in the victim, thus getting them to commit to accessing the link.

[img1]:https://steved3.io/images/posts/wp-phish-trap.png
