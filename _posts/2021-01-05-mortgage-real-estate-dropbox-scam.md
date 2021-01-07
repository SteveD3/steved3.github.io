---
layout: post
categories: phishing
title: Mortgage and real estate agents targeted by Dropbox scam
date: 2021-01-05
description: Criminals deployed a Dropbox Business phishing kit to target mortgage and real estate employees. The kit achieved near-instant results.
image: /images/phish-img.jpg
---

### Gone phishing

Sometimes, once a phishing kit is deployed, the criminal gets near-instant returns on their lure[^1], as victims start to click links and access the landing page[^2]. But it's hard to track these instances, because it isn't like criminals will publish their metrics on a regular basis. However, there are times when a criminal makes a mistake and leaves access logs on the compromised domain, which researchers like my self ultimately discover. When we do, the insight these logs offer is immense. Today, I figured I'd post about one example.

### Setting up the attacks

On December 9, 2020, a Dropbox Business phishing kit was uploaded to a domain promoting a vlog channel on YouTube. The domain, prior to this compromise, had a neutral reputation. But at some point the week of the 9th, a malicious actor compromised the domain and installed the phishing kit.

Deployment and initial testing took place at 2:07pm EST. I know this because the first entry in the logs is just random characters for the email address and password, and the logged IP address (Vypr VPN) was the only one recorded as a VPN. The other victim details in the logs were all on business IPs or residential IPs, suggesting they were at the office or working from home at the time the lure reached them.

### The logs and kit

The logs left on the server show that it took just 33 minutes for the first victim to arrive and fall for the scam. It isn't clear what kind of lure was used, or the context behind the lure, but the data in the logs confirm that the kit was targeting mortgage brokers and real estate agents. All of the logged victims worked in this industry, and some of them attempted to access the fake Dropbox Business portal more than once. The phishing kit itself shows that the lure likely included a reference to a PDF file of some kind, as victims were redirected to a benign website hosting a random PDF once the attack concludes. Given the quickness of the attack, it's clear the criminal already had their lure and victim list ready to go.

### The landing page

This is what the landing page looked like:

![Dropbox Business phishing page.][img1]

Once the landing page loads, the kit is looking to target email addresses, passwords, phone numbers, and geographic data such as IP, country of origin, and User-Agent details. The victim first enters their email address and password in order to access the website. Once this is done, the phishing kit will start the attack cycle, and email a copy of the victim's credentials to the criminals responsible for the scam. These credentials are also logged to the server, which is how I discovered them. The victim is then asked for their phone number. If given, that too is emailed to the criminals. After the attack ends, the victim is forwarded to a basic website and a random PDF file.

The email a criminal receives will look like this:

```
-----------{ DROPBOX LOGIN }-----------
Dropbox Email : contact@randomemail.com
Dropbox Pass : JohnnyPassword123!
-----------{ LOGIN INFOS}-----------
IP Address : 127.0.0.1
User Agent : Mozilla/5.0 (X11; Linux x86_64; rv:78.0) Gecko/20100101 Firefox/78.0
-----------{ DROPBOX }-----------
```

A visual flow of the attack is below.

### Attack overview (visual)
<script src="https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.min.js"></script>
<script>mermaid.initialize({startOnLoad:true});</script>

<div class="mermaid">
graph TD
A([Lure Dlivered])
-->|Victim Clicks Link| B{Landing Page Lodaded}
B --> |Victim Uses Login| C(Attack Starts)
C --> D(Credentials Emailed) & E(Credentials Logged to Server)
E -..-> |logs.txt| B
D & E --> F(Victim Asked for Phone Number)
F --> |Victim Shares Number| J(Phone Number Emailed)
J --> G(Attack Ends)
G --> H(Victim Forwarded to PDF)

style C fill:#80bcbf,stroke:#333,stroke-width:4px
style D fill:#bf809c,stroke:#333,stroke-width:4px
style E fill:#bf809c,stroke:#333,stroke-width:4px
style G fill:#80bcbf,stroke:#333,stroke-width:4px
style J fill:#bf809c,stroke:#333,stroke-width:4px
</div>

### Final thoughts

Targeted phishing attacks are rather common, as criminals usually tune their victim lists towards a general theme or topic, and the kits match it. In this case, the targeted victims were all business users, and the lure focused on a routine aspect of their jobs - receiving and sharing documents. Clearly, the attack worked, which is unfortunate. The domain hosting this scam is offline, but the URL is still being flagged by Google Safe Browsing.

---
[^1]: A lure is what entices the victim into clicking the phishing link. Often this can be an alarming message sent via email or SMS, or a post on social media. The key is that the criminal has created a sense of urgency, alarm, or curiosity in the victim, thus getting them to commit to clicking the link.

[^2]: A landing page is what is displayed when a victim click the phishing link within a lure.

[img1]:https://steved3.io/images/posts/dropbox_example.png
