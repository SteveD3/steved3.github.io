---
layout: default
categories: phishing
title: Fake AV phishing spikes in Q1 2022
date: 2022-03-07
description: There has been a noticeable uptick in the number of Fake Anti-Virus (Fake AV) phishing pages.
image: /images/stock/skull_red.jpg
---

There has been a noticeable uptick in the number of Fake Anti-Virus (Fake AV) phishing pages in Q1 2022. During my normal daily phishing scans, I rarely (if ever) come across the source code for these scam pages. Yet, during the first quarter alone this year, I've collected more than 50 samples targeting users on Windows and Apple devices.

The kits that have been collected so far are loosely based on a common development template, but with enough variation to keep them somewhat unique when it comes to flat detection. [Kit Hunter's detections](https://github.com/SteveD3/kit_hunter) for these scam pages were updated earlier this morning.

## Fake Anti-Virus
Fake AV scam pages have been around for about two decades, stretching back to the Windows XP days. They're often tied to Black Hat SEO scams, but the links to these domains can also be shared via forum and blog comments, instant messages, and social media.

If you're not familiar, Black Hat SEO scams take advantage of popular search terms in order to propagate malicious pages to the top of the SERP (Search Engine Results Page). Even today, it's common to see Black Hat SEO tactics tied to major news events or trending topics. In the heyday of browser-based attacks, Black Hat SEO was used to target software vulnerabilities to spread malware or trick people into loading Fake AV pages. Some of the more common targets back then include Internet Explorer and Adobe products, such as Flash, Shockwave, and PDF.

Fake AV falls under the category of a socially-based scam. So while Fake AV isn't a classic example of phishing, it is similar in style and function.

The scam relies on two key elements; a lack of technical understanding, and fear. The technical understanding element centers on a lack of knowledge related to computer operations and security, as well as a general misunderstanding on how support works. The fear element is straightforward, as many of the pop-ups and warnings on these scam pages present a pretext of system infection, moral exposure (e.g. porn), etc. Sometimes the Fake AV pages present a mix of problematic detections and exposures, depending on the developer and scope of the scam.

The attack format for Fake AV pages is mixed bag. Some of the scams request a download or install of some kind, while others (such as those observed recently) will ask the victim to "call" support and receive assistance.

If the scam is requesting an installer, there is no telling what the scammers are going to offer up. It could be malware, which harvests files and sensitive information from the infected system, or software that provides persistent access to the victim's system.

If the victim calls the number offered up on screen, this could compromise their personal and financial information, as well as present the scammers with an opportunity to install additional software on the victim's system, opening the victim up to additional attacks and annoyances.

## Fake Anti-Virus Examples

As an example of some of the variation seen in the kits that have been downloaded so far this quarter, here is a brief overview of the three most common. The top target, as seen in Figure 1, are Windows users.

![A Fake AV scam targeting Windows users][img1]
 **Figure 1:** A Fake AV scam targeting Windows users.

Each of the scams share some common tactics.

* The first is that the browser window will be filled with popups, alerts, and warnings that reference infections and even malware types. Sometimes the browser is pushed to full screen, and the victim will have difficulty reversing this change.

* The scams targeting Windows will leverage Windows Defender as the alleged security mechanism triggering the alerts. Windows Defender is a known brand, and if the name is Googled by the victim, the usage of the name on these scam pages is meant to provide instant legitimacy.

* Many browser elements are disabled, so the victim loses some control over their browser. Regaining function and control is problematic. This is intentional, as it is meant to replicate an infection.

* Finally, on some of these scam pages (such as the Apple page in Figure 2), a fake mouse pointer is rendered and mouse function is either disabled completely, or somewhat hindered. When this happens, the fake mouse pointer will move all around the screen. Again, this is supposed to imitate an infection.

![A Fake AV scam targeting Apple users, rendering a fake mouse pointer.][img2]
**Figure 2:** A Fake AV scam targeting Apple users, rendering a fake mouse pointer.

Another common element is the language switching. Many of the Fake AV scam pages I've observed contain code elements that render the text on the screen in the victim's local language. The translation is somewhat flawed, suggesting that a translation service was used instead of having a native speaker write the script (Figure 3).

>**Code Example - Language**
```
if (lang == "pt") document.getElementById("w2_4").innerHTML = "Terminado";
if (lang == "es") document.getElementById("w2_4").innerHTML = "Listo";
if (lang == "fr") document.getElementById("w2_4").innerHTML = "Effectué";
if (lang == "it") document.getElementById("w2_4").innerHTML = "Fatto";
```

![A Fake AV scam targeting Windows users in Japan.][img3]
**Figure 3:** A Fake AV scam targeting Windows users in Japan.

## Conclusion

Fake AV phishing is a somewhat common attack, but until lately, it wasn't at all common come across the source code powering these attacks. I'll continue to monitor the kits and note any changes to the kit functionality and indicators below. In the meantime, warn your non technical family and friends about these threats, and help them avoid possible exposure.

## Indicators

The following indicators are associated with the Fake AV kits that have been detected in Q1 2022.

>**Google Analytics:**
```
UA-116984914-2
UA-142500385-1
UA-146666754-1
UA-71647294-1
UA-77514673-1
UA-93923346-7
```

>**File Patterns and Formatting:**
```
Base filename for images:
5f205bb
5f205bc
```
>
```
Formatted as: base + six (6) random characters + _v .ext
>
5f205bbXXXXXX_v.gif | .png | .css
>
5f205bcXXXXXX_v.gif | .png | .css
```

>**Phone Numbers:**
```
(050) 5806-7793
(050) 5534-0312
+1-507-889-1818
+1(877) 337-3615
+1-888-202-9313
+1-(901)-810-3196
```

>**Mp3 Alerts**
```
alertms.mp3
0wa0rni0ng0.mp3
beep.mp3
err.mp3
mac.mp3
wa0lDErtm0s.mp3
warning.mp3
```

## Domains:
The following domains have been connected to the Fake AV scams observed in Q1 2022.
>
```
044lacked[.]ga
124iteration[.]ga
202configured[.]ga
244iteration[.]ga
303foeproweiw[.]ga
388gwowowka[.]ga
388hwpwodnf[.]ga
487owppaasj[.]ga
532gigabyte[.]ga
588gwpwoek[.]ga
935lacked[.]ga
dbchebdjej[.]ga
dhshdbwb[.]ga
djrbrdeth[.]ga
fhtvjdgjt[.]ga
gr494lapeorwgr[.]ga
hdbcgfnsnm[.]ga
rl939malwaring[.]ga
vhagyionvah[.]ga
whfjgjg[.]ga
```
>
>---
>
```
039bapwpdk[.]ml
042aoeowiwra[.]ml
388daowpwiw[.]ml
487hapqpwks[.]ml
584lurking[.]ml
638lapqkneps[.]ml
689lurking[.]ml
755gigabyte[.]ml
ejgdhvdf[.]ml
gr245gigabyte[.]ml
ib309madenaing[.]ml
nvbchdnvd[.]ml
rw424bundling[.]ml
yk498partically[.]ml
```
>
>---
>
```
alexacartbox[.]online
balluthree[.]online
ci48nco[.]online
gloweranew[.]online
greatofalltime[.]online
lutinswipinfo[.]online
msg67jp8[.]online
onegoalsearch[.]online
otherservicesdomains[.]online
teamhourisimportant[.]online
```
>
>---
>
```
dfgjdfgjdf1[.]xyz
dpillsnewgofit[.]xyz
expediagrouping[.]xyz
fghsdfghdgh7[.]xyz
letmefityou[.]xyz
```
>
>---
>
```
cleaningkyotoservices[.]digital
priceamazing[.]digital
priceexcelsheet[.]digital
```
>
>---
>
```
3mjbfdmvn[.]shop
claimeventgameterbaru[.]duckdns[.]org
passagiert[.]cf
rytjghsbdghjjh5[.]sbs
```

[img1]:https://steved3.io/images/posts/fake-av-top.jpg
[img2]:https://steved3.io/images/posts/fake-av-mac.jpg
[img3]:https://steved3.io/images/posts/fake-av-jp.jpg
