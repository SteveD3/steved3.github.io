---
layout: post
categories: phishing
title: Fast Phishing - Criminals see near-instant results
date: 2021-01-05
description: Sometimes, once a phishing kit is deployed, the return for the criminal responsible is immediate. I recently discovered a phishing kit that had intact victim logs, which offered an interesting look at the mechanics of an attack.
image: /images/phish-img.jpg
---

### Gone phishing




### Attack overview
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
