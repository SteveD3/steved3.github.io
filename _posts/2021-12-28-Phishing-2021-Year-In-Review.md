---
layout: default
categories: general
title: Phishing 2021 - A Year in Review
date: 2021-12-28
description: I took the month of December off, and after a week, I needed something to do. So, I built a website to teach myself a few things, and this is the first post.
image: /images/stock/phishing_keyboard.jpg
---
## Phishing is still a major problem

As the year comes to a close, I thought I’d look at my phishing research and offer up some thoughts and details concerning the state of things, as well as take a look at some of the interesting bits I’ve observed over the last twelve months. If the year has taught me anything, it’s that phishing is still a problem, and it’s one that isn’t going away any time soon.

All throughout 2021, I’ve been working on maintaining Kit Hunter. [Kit Hunter is my Python project](https://steved3.io/data/Kit-Hunter-Version-2.0/2021/09/06/) that aims to help system admins protect their websites and servers. The project took off, and in September I released a massive update that included a number of requested functions, as well as a complete overhaul to its core functionality. Yet, in order to [maintain Kit Hunter](https://steved3.io/data/Kit-Hunter-2.0-Getting-Started/2021/09/07/), I need to constantly test the application, as well as its detection models.

To do this, I need to collect phishing kits.

## By the Numbers

>**Disclaimer:** The data used in this report was collected between 01 January 2021 and 06 December 2021. The early cutoff gave me time to compile information and write the report. As such, Q4 2021 is only two-thirds of the way complete. I would also like to thank the following people who helped me with research, writing, code, or just in general over the last year, including my editor Amanda. Their Twitter handles are below.
>
>```@AmandaFGoedde``` ```@nullcookies``` ```@dyngnosis```
>```@olihough86``` ```@dave_daves``` ```@JCyberSec_```
>```@n0p1shing``` ```@ANeilan``` ```@selenalarson```
>```@sysgoblin``` ```@PaulWebSec``` ```@BushidoToken```
>```@sjhilt``` ```@phage_nz```


In 2021, I collected over **5,000 phishing kits**, which gave me some unique insight into development practices, criminal economics, deployment, and infrastructure. In addition to the phishing kits themselves, I also got lots of logs, which offers a limited view into victimology. Mostly I focused on browsers and device ID, given that the majority of the victims to the websites where I obtained the logs came from the United States, U.K, or Europe.

In total, I scanned just over **3.8 million domains** this year, averaging about **11,000 domains per day**. All told, I spent more than 440 hours scanning domains.

| 2021 Quarterly Totals   	 |   Q1       |    Q2      	|    Q3      	|    Q4      	|
|--------------------------- |-----------	|-----------	|-----------	|-----------	|
| Total Scan Time            | 106:46:35 	| 139:16:10 	| 107:15:04 	| 88:25:29 	  |
| Average Daily Scan Time  	 | 1:11:12   	| 1:31:48   	| 1:09:41   	| 1:18:03   	|
| Total URLs Scanned       	 | 1,033,365 	| 1,051,815 	| 1,009,827 	| 714,961 	  |
| Average Daily URLs Scanned | 11,489     | 11,559      | 10,969      | 10,814      |
| Phishing Kits Collected    | 1,472      | 1,458       | 1,210       | 914         |

Most of my work is automated, but I do manually check domains as well, which sometimes increases my daily phishing kit count. I use [Miteru for my URL scanning](https://github.com/ninoseki/miteru), and it works great. Miteru uses all of the common feeds from [URLScan](https://urlscan.io/) (CertStream, OpenPhish, PhishTank, URLhaus), as well as PhishStats, and Phishing Database.

In short, it was a productive year.

## Log Traffic

I sometimes collect log information from my searches, which records details on the victim of a given phishing attack. If there is personally identifiable information (PII) and credentials in the logs, I report the information to the targeted brand. The only log data I keep concerns device details and geolocation. The geolocation data isn’t all that interesting, as the majority of victims came from the United States, UK, or Europe, with a few other countries added in for good measure, but not at the volume of the top three.

But when it comes to the device information, there are a lot of details to unravel. For example, iOS was the top operating system in the logs, which makes sense considering that many phishing kits target mobile users.

The iPhone was followed by Macintosh, as MacOS was the second most popular operating system. Linux (Ubuntu) was third, which could indicate the presence of researchers or automated security scanning. Finally, Windows was the fourth most common operating system observed.

There was a wide range of browsers within the logs, as Safari, Firefox, Edge, Opera, and Chrome (in no particular order) all made an appearance. The browser versions were (for the most part) all recent releases, or versions that were within a patch or two of being current. Still there were more than a few browsers that were end-of-life, which makes sense considering the operating system / device breakdown.

## Operating Systems
#### Android
The oldest version of Android in the logs was 4.0 (followed by versions 5 and 6), but the more common versions were 7.x and 8.x, on Samsung devices. This was followed by Android versions 9, 10, and 11. Samsung was the most common device seen for Android, but Motorola, OnePlus, HTC, and Huawei all appeared in the logs.

#### iOS
On the iPhone, iOS 11 was the most common version found in the logs, followed by versions 14 and 13. Combined, the three iOS versions were seen over 1,000 times in the logs. The oldest version was iOS 6, which was found only three times.

#### Linux
Named distribution wise, Ubuntu was the top record in the logs for Linux. However, other versions were well represented, but without a branded name on the headers. This leads me to speculate that the traffic came from researchers or scripted scanners, which were running on Linux and using Chrome, the most popular browser build recorded with this operating system.

#### Windows
It will come as no shock to learn that Windows 10 was the most common version of Windows seen in the logs, but what did stand out was the fact that Windows 8, Windows 7, Server 2003, Vista, and even Windows XP all made an appearance. Edge was a common browser among the builds, but because of the age range, there were also instances of Internet Explorer in the mix. This is in addition to the usage of Firefox and Chrome.

## Targeted Brands
Criminals running phishing campaigns are always spoofing one brand or another. But they’re not perfect. Often, a kit will be developed for one brand, and then altered slightly to target a similar brand.

A good example of this are some of the kits targeting United Parcel Service (UPS) and the United States Postal Service (USPS). The USPS kits were first, leveraging a missed delivery scam in order to get victims to share personal information and financial data. The scams were successful, so the criminals altered the USPS kits slightly and moved on to target UPS as well.

There were a few interesting elements of overlap in these kits, showing a process where development is hurried along in order to get the final product out the door as quickly as possible. Think of it as a rushed “go-to-market” strategy.

![A UPS phishing kit still contains elements of the USPS phishing kit it was built on.][img1]

**Figure 1:** A UPS phishing kit still contains elements of the USPS phishing kit it was built on.

>1. Many of the CSS elements used on the UPS kits were pulled directly from the USPS website itself. In reality, these elements don’t exist on the UPS domain. The Informed Delivery option, and mailman logo seen in the top part of Figure 1 is an example of this.
>
>2. The footer on the phishing page contains both UPS and USPS elements. Care was taken to get the branding in place, but it feels as if the developers used the replace function in Notepad and just swapped out some text and image elements. A whole section related to USPS websites, including the National Postal Museum are clearly present on the UPS kits.

Other notable shipping scams in my collection this year include FedEx, Post and Parcel, PostPay, and Royal Mail.

#### Social Brands

The top social brands in my phishing collection this year were Facebook, WhatsApp, and LinkedIn, but that doesn’t exclude services like Twitter, Flickr, Match, OurTime, Daum, Naver, Sina, as well as 163 and 126.

Targeting social media is a big deal for criminals running phishing campaigns, because people often recycle passwords between social accounts, or they use easily guessed variations. Not to mention, compromising a social account can lead to additional victims, as the trust dynamic between people online can be exploited. There’s also the fact that for professional networks, like LinkedIn, compromising an account can expose other people, corporations, and their professional partners.

#### ISPs and Tech Services

This type of phishing, excluding Microsoft Office, was a massive focal point as the year went by. Brands such as Spectrum, Netflix, WeTransfer, Dropbox, AT&T, Comcast (Xfinity), Salesforce, Optus, Frontier, Spotify, Wowway, Deloitte, Rackspace, DocuSign, Orange, and GoDaddy, just to name a few.

Dropbox and DocuSign were the most common, given their connection to corporate phishing, which is a high-value phishing target. On the home front, Netflix was the main consumer target. ISPs were quite common as well. But nothing - absolutely nothing - tops the number of Microsoft Office kits collected this year.

>**Microsoft was the number one targeted brand**, as criminals developed and pushed several variants of kits targeting Office 365 and OneDrive.
Using just the Microsoft detections from Kit Hunter, with no other branding detections or URL detections, a scan of my collected phishing kits returned 2,640 results.
>
>This means that **52% of the phishing kits scanned were related to Microsoft Office in some way**, either directly or by leveraging elements of Microsoft Office in the attack.

Given the widespread use of Microsoft Office, criminals will add Office 365, OneDrive, or SharePoint elements to phishing kits targeting DocuSign and Dropbox. So it is possible that some of the kits I scanned targeted one or more of these brands.

Corporate phishing is a big deal, because valid and verified accounts can be collected or sold to others, who then use this access for additional attacks, up to and including ransomware. There is a whole “business cycle” in the criminal world dedicated to this type of byproduct of phishing. However, phishing is only part of the process. Access brokers will leverage phished credentials, but they also focus on vulnerable systems and services. So while phished credentials are a major risk, they're not the only risk a given company will face.

#### Banking

Outside of phishing attacks targeting Microsoft Office users and consumer tech brands, the other major theme this year focused on banking. Phishing in the financial services industry is huge, and a main focal point for criminals operating in the phishing space.

Such attacks offer up access to personal and financial information in one go, and criminals will sometimes use the compromised banking accounts for other types of fraud, including card fraud, retail fraud, in addition to other types of financial fraud, where victim accounts and personal information are leveraged laundering schemes.

Here is a breakdown of the top financial phishing kits collected this year.

1. PayPal
2. Chase
3. American Express
4. Crédit Agricole
5. Wells Fargo
6. Citi
7. La Banque Postale
8. Bank of America
9. USAA
10. HSBC

In addition to the top 10, other banks include TD Canada, Halifax, Santander, PNC, CIBC, Huntington, Fifth Third Bank, RBC Royal Bank, Regions Bank, KeyBank, BECU, Alaska USA, Square, Cashapp, TurboTax, QuickBooks, and Capital One.

Moreover, crypto currencies were a popular target, with Coinbase being the leading brand targeted in that space. Brands like Credit Karma, Equifax, and TransUnion also had kits discovered this year, proving that criminals target the financial sector across a wide spectrum of brands and services. There’s absolutely nothing they won’t try and get their hands on.

## Pandemic Phishing
In early 2021, I came across several phishing kits targeting pandemic unemployment assistance (PUA) programs. These are programs designed to assist those who needed help during the COVID-19 lockdowns, and were essential services for millions of Americans.

One of my finds led to a spot on CBS News that aired across the country. In that story [(which you can read here)](https://www.cbsnews.com/news/phishing-scam-targeted-unemployed-new-yorkers-during-pandemic) I discussed an unemployment phishing kit targeting people in New York. I explained how criminals were collecting and selling personal information compromised in the scam, and shared examples of ads on various criminal markets that were related to the types of data these phishing kits were after.

In addition to New York, I’ve since discovered PUA scams targeting people in Wisconsin, Pennsylvania, and Massachusetts.

![Examples of PUA scams targeting people in New York and Wisconsin.][img3]

**Figure 2:** Examples of PUA scams targeting people in New York and Wisconsin.

Phishing in 2020, as COVID-19 lockdowns started to take hold and the public was gripped by daily reminders of the health risks and scarcity of basic goods and services, became a strange place. All of the normal expected phishing attacks remained, from finance to social media, and streaming media, as well as gaming. However, criminals started to focus their efforts on topical things as well, but only passively.

There were half-assed attempts to leverage COVID-19 and the public's drive to obtain information or access to a vaccine. These attempts were somewhat successful, as they drove traffic to the domains, but the final result was a generic email phishing attempt. The image below is an example that leveraged the Centers for Disease Control and Prevention (CDC) and the Department of Energy in the United States.

![An image showing a basic email phishing scam leveraging the CDC and COVID-19.][img6]

**Figure 3:** A basic email phishing scam leverages the CDC and US Department of Energy.

As 2021 rolled around, criminals shifted their COVID-19 phishing operations towards vaccines, and combined this with financial and data collection elements. These attacks were more focused, and leveraged pressure points, such as imposing a strict deadline for action. The image below focuses on the National Health Service (NHS) in the United Kingdom.

![An image showing a vaccine invite from the NHS.][img7]

**Figure 4:** Victims are invited to apply for access to a vaccine, but warned that they have 24-hours to register, else they will lose their access to the program completely.

The NHS scam is the one that stands out to me, as it shows critical thinking and planning on the part of the criminal. Victims were led to these phishing kits via email or SMS, and once the page was loaded, it looked like a legitimate NHS portal. The branding, design elements, even the coloring was an exact copy.

The critical thinking elements included the fact that existing talking points by the NHS at the time were leveraged in the phishing kit’s script. For example, the fact that a second vaccine dose would take place 11 to 12 weeks after the first dose. At the time this phishing scam was circulating, that was the current thinking. Now, the NHS recommends 8 weeks for those 18 years of age or older, and 12 weeks for those aged 16 or 17.

The script also included an element of exclusivity, as victims were told they could only use the service if they received an email or SMS regarding their invitation, adding that they are “required to reply to this invitation within 24 hours of this notification.”

If the victim was successfully hooked, the scam continued and they were directed to complete a form that included personal information, such as address, mobile phone number, mothers maiden name, and birthdate. From there, they were directed to a financial form that collected banking details and credit card information. Once all of that was submitted the victim was directed to the actual NHS website.

It isn’t clear how successful these campaigns were, but the timing of them is what made them memorable. Criminals will always find a way to leverage large events or circumstances, and this is a perfect example of that.

## Obfuscation and Control

While developing their phishing kits, criminals go to great lengths to hide their activities. From redirection scripts, to various types of blocking mechanisms targeting scanners, security vendors, and even researchers like myself, criminals are constantly developing new security tools. Here are a sampling of some of their methods

#### Redirection

In the example below, we see a redirection page, which is actually part of the main phishing kit. Here the criminal stands up a landing page on a domain that is different from the one used for the actual phishing attack. This keeps the main domain hidden, while enabling them to shift landing domains as needed.

At the time this report was being written, this particular redirection script had been seen 82 times, making it one of the more common methods seen with kits targeting Chase bank.

![The redirection landing page is used to hide the main domain used for the phishing attack.][img2]

**Figure 5:** A redirection page is used to protect the main domain used for the phishing attack.

#### Configuration

Another way criminals obfuscate and control victims to their phishing kits is through the use of targeted controls. Criminals use these controls to determine things like who can access the phishing kit’s landing page, how often they can visit, how data is collected, as well as what sort of data is collected, and more.

Below is a sample configuration file from a kit targeting Citizens Bank:

````
"log_user"  => "1",         // Log User-Agent, IP and Date
"phone_lookup"  => "1",     // Phone API Lookup
"zip_lookup"  => "1",       // ZIP Lookup
"print_match"  => "0",      // Print Crawler Detections
"anti-back"  => "1",        // Victim Can't Go Back To Session
"debug"  => "0",            // Print Errors
"proxy_block"  => "1",      // Detect Proxies & Block Them
"send_mail"  => "1",        // Send E-Mail To Your Mail
"Save_results"  => "1",     // Save Results
"telegram"  => "0",         // Telegram Bots Receiver
"double_login"  => "0",     // Double Login
"double_qa"  => "0",        // Double Questios
"double_email"  => "0",     // Double Email
"country"  => "US",         // Target SPAM Country
"chat_id"  => "",           // Chat ID Of You
"bot_url"  => "bot",        // Your Bot API Key (ADD "bot" BEFORE API KEY)
"api_key"  => "901xxx",     // API Key Numerify.com
"zip_api"  => "36xxxx",     // API Key zipcodebase.com
"referer"  => "hxxps://live.com/",      // HTTP Referer For Antibots
"out"  => "citizen+login",        // Outcome Of AntiBots Forward - DONT CHANGE
"email"  => "your@email.com",     // Your E-Mail
````
With this configuration file, the criminal will configure various elements. Included in the options are telephone verifications, and address verifications. These verifications help ensure that the data collected is both accurate, and complete. Criminals will collect and trade or resell this information, and the more accurate it is, the more valuable it is.

The configuration also has proxy detection and blocking, crawler detection and blocking, error logging, and geolocation targeting. In the case of geolocation, the phishing kit will only allow victims in the United States to connect. The proxy and crawler blocking helps keep the phishing kit alive longer by avoiding the people and tools that hunt for such threats and get them taken down.

This configuration will also control how the victim’s information is sent to the criminal. Normally phishing kits will email the victim’s data to the criminal, but this kit has another option outside of email - Telegram.

#### Telegram

I started seeing Telegram-based data exfiltration as far back as December 2020. At the time, the option was available, but not really used in the phishing kits that were coming into my collection. Then in January 2021, all of that changed. To date, **I have identified more than 300 unique Telegram IDs** based on my phishing kit collection. There is more that can be done with Telegram, but the exact nature of that isn’t something I’m going to put in a blog post. Researchers who have questions are free to find me in the usual haunts and ask away.

#### Third-party Tools

Criminals use a lot of legitimate third-party tools in their development cycles and functionality. They do so for the exact same reasons that legitimate users wish to leverage these services. For one, they're cheap, and two - they work. Google forms is one of the more popular services, especially in the cryptocurrency phishing arena, but there are others out there that I want to examine.

**Firebase**

Firebase is a backend-as-a-service (BaaS) platform that was acquired by Google in 2014. You see this turn up in a lot of phishing kits, particularly the ones that leverage API storage, verifications, and other aspects of “cloud” in the kit development cycle. One of the first kits I recall seeing this in was a phishing kit type that would later be called LogoKit [after researchers at RiskIQ made its existence publicly known](https://community.riskiq.com/article/a068810a). Within LogoKit, Firebase is used as a common object storage mechanism.

At the time this report was written, I’ve collected 156 phishing kits leveraging Firebase in some way.

**LogoKit**

As mentioned, LogoKit was publicly exposed in January of this year, but some of the earliest samples I’ve collected date back to November of 2020. (The usage of ```logo.clearbit.com``` has been around in my collection since June 2020)

The functionality of the kit has been recycled by many phishing kit developers too. The process is simple and effective. Operating on the presentation layer (DOM), the script is able to alter the visible content and form data on a given page without any user interaction. Also, because the kits are often developed with legitimate services, and the logos used are authentic, there is an implied level of trust pushed towards the victim.

At the time this report was written, I’ve collected more than 1,200 kits this year that leverage elements of the LogoKit code, or complete LogoKit deployments themselves. The code is leveraged in a number of phishing schemes, targeting Microsoft Office, banking and finance, as well as consumer-level phishing, such as social media and gaming.

![LogoKit source code, taken from a Microsoft Office phishing kit deployed in November, 2020.][img4]

**Figure 6:** An example of LogoKit source code, taken from a Microsoft Office phishing kit deployed in November, 2020.

**JayBizzle**

Open source code is a wonderful thing. It’s used in products great and small, and while it can sometimes cause headaches for those in the security industry, on the whole open source has made the internet better. But like anything else, open source code can be abused, and that is exactly what happened with [Crawler Detect](https://github.com/JayBizzle/Crawler-Detect).

Criminals have started leveraging  Crawler Detect to block out scanners and other bots from their phishing domains, including security crawlers. The usage has a moderate success, but it isn’t foolproof. Still, it’s an example of phishing kits leveraging existing technologies and processes, instead of reinventing the wheel.

But don’t get it twisted, I’ve seen some strange anti-bot scripts used in phishing kits this year that either don’t work, or rely on outdated details and information. Some scripts just block whole netblocks, which works, but not in the way it was likely intended. The point is, criminals go to a lot of trouble to hide their activities, and if someone develops a useful tool that inadvertently aids them, they’ll use it with no hesitation.

![Criminals love to use open source software in their phishing kits, such as this example leveraging Crawler Detect.][img5]

**Figure 7:** Criminals love to use open source code in their phishing kits, such as Crawler Detect by JayBizzle.

## The Curious Ads

Phishing kit developers often work in groups, they code and develop as sort of a team sport, with each developer trying to gain a reputation for being the one who can code the sickest kits that are FUD - fully undetectable. However, they also freelance their development talents, and will code custom projects for people who are willing to pay. Now, these transactions are often conducted on private forums, closed groups, or direct messages. But sometimes, you come across public offers.

The final thing I have to share today related to my phishing research this year, are some ads from Fiverr. The first image represents one of three profiles discovered in March of 2021. I am pretty sure a single person created all three accounts in order to drum up some development work, as the biography details were nearly identical. I really doubt they succeeded.

![A Fiverr account offering to develop customized phishing kits.][img8]

**Figure 8:** A person on Fiverr has offered to develop custom phishing kits.

In this example, the person on Fiverr has three tiers of code they are willing to develop. The first, which sells for $55 USD, will contain a single page with a login box, and the victim’s credentials will be stored within a text file, database, and email. For $105 USD, the offer adds an additional page. For $140 USD, the offer extends to three pages in total, but the seller does encourage contacts in order to price out different custom order options.

The accounts have been banned, but it is still possible to find similar offers on the website, such as this one.

![A Fiverr account discovered in December, 2021 offering to develop customized phishing kits.][img9]

**Figure 9:** An account on Fiverr discovered in December, 2021 offers to develop custom phishing kits.

Same deal, only this seller offers different pricing $80-$220 USD, and different features. Their offer is centered on financial scams, with a promise to capture banking details, card details, and even offer a redirection link. For the max price, you can order “all types of pages” from this individual.

## Conclusion
These days, phishing is a part of the first wave of attacks against a person or organization, and it’s improved over the years to increase its effectiveness. As I wrote in a report for my dayjob once:

>Gone are the days of basic cloned websites. Today, phishing is a turnkey business, even offered as a hosted solution for criminals who wish to leverage phishing-as-a-service developments...

The criminal economy is a powerful one, and phishing is absolutely a major part of it.

The reality is this, phishing is one of those problems that doesn’t really have a silver-bullet fix, because there are so many moving parts. It’s hard to predict what criminals will do next. Not only that, but since humans are still an important aspect in phishing, they will remain somewhat of the weakest link in the chain.

#### Business Defense

While the opening to this section comes off as doom and gloom, it isn’t meant to be. That’s just reality. It doesn’t mean that defenders can’t take action. Phishing has been an element in many security incidents over the last several years, because it’s effective. Phishing in the corporate world takes advantage of a victim’s workflow, as well as other things such as password reuse, a lack of multi-factor authentication, and loose email / transactional policies. Attacks on this front have led to W2 records being compromised, threat actors gaining elevated privileges on the network, and malware (i.e. ransomware) being installed. All because of phishing.

So yea, people might be the weakest link in some cases, but they can also be the single largest line of defense. Train them to spot and (most importantly) report anything they suspect as phishing. Sure, until you get things sorted, there will be false positives, but it’s worth it because you can train staff in an active environment.

When conducting phishing training, remember to test corporate attacks and consumer ones. Your staff are consumers too, and they can easily be attacked outside of the office, so make sure training covers as much as possible, and make sure that it’s ongoing.

#### Home users

I cannot stress the importance of using 2FA and password managers enough. These defenses are critical, and they work well too, because criminals are developing processes and techniques to bypass them.
2FA bypasses are not foolproof attacks however, so criminals deal with more losses than successes. Reading between the lines, yes there are ways that 2FA can be bypassed, but that doesn’t mean the protection isn’t worth using.

While on the topic, before the question is asked, no you shouldn’t use SMS as a means of authentication. But I say that with a bit of a “BUT” tone, because if SMS is all you have, then you need to use it and encourage your service provider to abandon it in favor of something stronger.

As for password managers, not only can they help by triggering an instant red flag (because a password manager won’t auto-fill a phishing website’s username and password fields), they make it hard for a criminal to guess or crack your password if a service is ever compromised.

Phishing is a hard battle to fight, but there are tools out there that can help, but you have to use them. That’s the key. You have to use them.

Thanks for taking the time to read this.

[img1]:https://steved3.io/images/YIR/figure_1.jpg
[img2]:https://steved3.io/images/YIR/figure_2.jpg
[img3]:https://steved3.io/images/YIR/figure_3.jpg
[img4]:https://steved3.io/images/YIR/figure_4.jpg
[img5]:https://steved3.io/images/YIR/figure_5.jpg
[img6]:https://steved3.io/images/YIR/figure_7.jpg
[img7]:https://steved3.io/images/YIR/figure_8.jpg
[img8]:https://steved3.io/images/YIR/figure_6.jpg
[img9]:https://steved3.io/images/YIR/figure_9.jpg