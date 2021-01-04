---
layout: post
categories: phishing
title: Phishing Research project
date: 2021-01-03
description: Some of the research I've started doing lately focuses entirely on phishing and phishing kits. Here are some quick observations.
---

I started doing some research during my December vacation, and focused my efforts almost entirely on phishing and phishing kit development. It's an interesting process, because no two kits are alike, even if the same person developed them. There's always a slight variation somewhere, and as kits get recycled or copied, they become this hodgepodge of code and variables.

That's another interesting thing. There is no honor among thieves, so when one phishing kit developer comes up with a new design or process, it's quickly stolen (ripped) and you'll see it appear in multiple kits a short while later. There is also a wide variety of brands being targeted with the kits I've collected. All the usual brands are there, such as Chase or Wells Fargo, Office365, Netflix, PayPal, etc. However, there are other smaller, more localized brands being targeted, which is interesting to observe.

From November 2020 until December 31st, I collected 810 phishing kits for my research. This is in addition to the hundreds of kits I already had. I'll start digging into them in more detail, but the list below is a brief example of the things I've extracted from my phishing collection.

```
.
├── 1-and-1
│   ├── nov-2020-1n1
│   └── nov-2020-1n1-2
├── ABSA
│   └── july-2019-absa
├── Adobe-PDF
│   ├── aug-2019-PDF
│   ├── nov-2020-adobe
│   ├── nov-2020-adobe-2
│   ├── nov-2020-pdf
│   ├── nov-2020-pdf-2
│   └── nov-2020-pdf-3
├── ADP
│   └── nov-2020-adp
├── AirBNB
│   └── sept-2019-airbnb
├── Alibaba
│   ├── july-2019-alibaba
│   └── oct-2019-alibaba
├── Amazon
│   ├── aug-2019-amazon-xbalti
│   ├── aug-2019-amazon-xbalti-2
│   ├── aug-2020-Amazon-FreakzBrothers-Cracked
│   ├── july-2019-amazon
│   ├── may-2020-amazon
│   ├── nov-2020-amazon
│   └── sept-2020-amazon
├── American_Express
│   ├── april-2020-amex
│   ├── june=2020-amex
│   ├── may-2020-amex
│   └── may-2020-amex-2
├── AOL
│   ├── feb-2020-aol
│   ├── march-2020-aol
│   └── oct-2018-aol
├── Apple
│   ├── aug-2019-apple
│   ├── aug-2020-apple
│   ├── dec-2019-apple
│   ├── dec-2019-apple-iforgot
│   ├── dec-2019-apple-itunes
│   ├── dec-2019-apple-mapconnect
│   ├── july-2020-ios
│   ├── june-2019-apple
│   ├── may-2019-apple-hijaiyh
│   ├── nov-2019-apple
│   └── nov-2019-apple-16shop
├── AT&T
│   ├── jan-2020-att
│   ├── july-2019-att
│   ├── nov-2019-att
│   ├── nov-2020-att
│   └── nov-2020-att-2
├── Bank_of_America
│   ├── aug-2019-bank-of-america
│   ├── aug-2019-bank-of-america-2
│   ├── july-2019-bank-of-america
│   ├── july-2019-bank-of-america-2
│   ├── may-2020-bank-of-america
│   ├── nov-2019-bank-of-america
│   ├── nov-2020-bank-of-america
│   ├── nov-2020-bank-of-america-2
│   └── nov-2020-bank-of-america-3
├── Bank_of_Guam
│   └── oct-2020-guam
├── Bell
│   └── dec-2020-bell
├── Blockchain
│   ├── aug-2019-vbittrex-bitcoin
│   ├── dec-2020-coinbase
│   ├── jan-2020-blockchain
│   └── march-2020-coinbase
├── BNP Paribas
│   └── nov-2020-paribas
├── BT
│   └── oct-2018-BT
├── Chase
│   ├── CH4S3EMPIR3
│   ├── jan-2020-chase
│   ├── july-2019-chase
│   ├── july-2019-chase-2
│   ├── june-2020-chase
│   ├── may-2020-chase
│   ├── may-2020-chase-2
│   ├── nov-2020-chase
│   ├── nov-2020-chase-2
│   ├── nov-2020-chase-3
│   ├── nov-2020-chase-4
│   ├── nov-2020-chase-5
│   ├── nov-2020-chase-6
│   ├── oct-2018-chase
│   ├── oct-2019-chase
│   ├── sept-2020-chase
│   └── sept-2020-chase-2
├── Citi
│   └── aug-2019-citi-bank
├── Citrix
│   └── feb-2020-citrix
├── Comcast
│   ├── march-2020-comcast
│   ├── nov-2020-comcast
│   └── sept-2020-comcast
├── Co_Operative_Bank
│   └── may-2020-co-operative-bank
├── Costco
│   └── july-2019-costco
├── COVID-19
│   └── april-2020-covid
├── cPanel
│   ├── nov-2020-cpanel
│   ├── nov-2020-cpanel-2
│   └── nov-2020-cpanel-3
├── credit-agricole
│   └── sept-2020-cole
├── DHL
│   ├── july-2019-dhl
│   ├── july-2019-dhl-2
│   ├── july-2019-dhl-3
│   ├── june-2020-dhl
│   ├── nov-2020-dhl
│   ├── nov-2020-dhl-2
│   └── nov-2020-dhl-3
├── Discover
│   ├── july-2020-discover
│   ├── july-2020-discover-2
│   └── june-2020-discover
├── DocuSign
│   ├── nov-2020-docusign
│   ├── nov-2020-docusign-2
│   ├── nov-2020-docusign-3
│   ├── oct-2018-docusign
│   ├── oct-2018-docusign-2
│   └── oct-2018-docusign-3
├── Dominos
│   └── july-2020-dominos
├── Dropbox
│   ├── nov-2018-dropbox
│   ├── nov-2018-dropbox-2
│   ├── oct-2018-dropbox
│   └── oct-2018-dropbox-2
├── eBay
│   └── nov-2020-ebay
├── eSign
│   └── nov-2020-esign
├── Facebook
│   ├── dec-2020-facebook
│   ├── nov-2020-facebook
│   └── nov-2020-facebook-vn
├── FI-Bank
│   └── nov-2020-fibank
├── FirstAmerica
│   └── nov-2020-firstamerica
├── FirstBank
│   └── dec-2020-first-bank
├── Fontier
│   └── oct-2020-frontier
├── Foreign_Investment_Review_Board
│   └── nov-2020-FIRB-AU
├── Generic_Email
│   ├── april-2019-generic-email
│   ├── aug-2019-generic-email
│   ├── dec-2019-generic-email
│   ├── jan-2020-generic-email
│   ├── july-2019-generic-email
│   ├── july-2019-generic-email-2
│   ├── june-2020-generic-email
│   ├── june-2020-generic-email-2
│   ├── nov-2020-generic-email-001
│   ├── nov-2020-generic-email-002
│   ├── nov-2020-generic-email-003
│   ├── nov-2020-generic-email-004
│   ├── nov-2020-generic-email-005
│   ├── nov-2020-generic-email-006
│   ├── nov-2020-generic-email-007
│   ├── nov-2020-generic-email-008
│   ├── nov-2020-generic-email-009
│   ├── nov-2020-generic-email-010
│   ├── nov-2020-generic-email-multi
│   ├── nov-2020-roundcube
│   ├── oct-2018-generic-email
│   ├── oct-2018-generic-email-2
│   ├── oct-2019-generic-cn4e
│   ├── oct-2019-generic-core
│   └── sept_2019-cisco
├── Generic_File_Sharing
│   └── april-2020-file-share
├── Generic_Mailer_Scripts
│   └── july-2019-gen-mailer
├── Generic_Phishing
│   ├── dec-2019-multiple-banks
│   ├── july-2020-generic-phishing
│   ├── july-2020-generic-phishing-2
│   ├── march-2020-gen-phishing-sns
│   ├── march-2020-multiple-banks
│   ├── may-2019-generic-intl-card-service
│   ├── may-2019-multiple-banks
│   ├── may-2020-multi-kit-collection
│   ├── may-2020-tech-support-scam
│   ├── multiple-kit-phishing-collections
│   ├── nov-2019-multiple-kits
│   ├── nov-2020-anti-bot
│   ├── nov-2020-argentina
│   ├── nov-2020-argentina-2
│   ├── nov-2020-banking
│   ├── nov-2020-banking-2
│   ├── nov-2020-generic-banking
│   ├── nov-2020-generic-intl-card-service
│   ├── nov-2020-south-korea-phishing
│   ├── nov-2020-south-korea-phishing-2
│   ├── nov-2020-south-korea-phishing-3
│   ├── oct-2018-south-korea-phishing
│   ├── sept-2020-gen-phishing
│   └── sept-2020-gen-phishing-id
├── GlobalSources
│   └── nov-2020-globalsources
├── GoDaddy
│   ├── aug-2019-godaddy
│   └── july-2019-godaddy
├── Google
│   ├── feb-2020-google
│   ├── march-2020-gmail
│   ├── nov-2018-google
│   └── oct-2018-gmail
├── Halifax
│   ├── nov-2020-halifax
│   ├── nov-2020-halifax-2
│   ├── nov-2020-halifax-3
│   ├── sept-2020-halifax
│   └── sept-2020-halifax-2
├── HMRC
│   └── dec-2020-hmrc
├── HSBC
│   └── july-2020-hsbc
├── Huntington
│   └── june-2020-huntington
├── ING
│   └── june-2020-ING
├── Instagram
│   ├── Mobil_Uyumlu_Mavi_Tik_Scripti_v3.0_55utd55
│   └── STALKER-BEDO_SCRIPTI
├── Interac
│   ├── aug-2019-interac
│   ├── aug-2019-interac-2
│   ├── july-2019-interac
│   └── july-2019-interac-2
├── Komail
│   └── july-2019-komail
├── Liberty_Mutual
│   └── aug-2019-libertymutual
├── LinkedIn
│   ├── nov-2020-linkedin
│   ├── nov-2020-linkedin-2
│   ├── nov-2020-linkedin-3
│   ├── oct-2019-LinkedIn
│   └── sept-2020-linkedin
├── Lloyds
│   └── nov-2020-lloyds
├── Microsoft
│   ├── aug-2019-Office365
│   ├── dec-2019-office
│   ├── feb-2020-microsoft
│   ├── feb-2020-microsoft-voicemail
│   ├── jan-2020-sharepoint
│   ├── july-2019-office365
│   ├── july-2019-office365-2
│   ├── july-2019-office365-3
│   ├── july-2019-sharepoint
│   ├── march-2020-owa
│   ├── nov-2020-excel
│   ├── nov-2020-excel-2
│   ├── nov-2020-office
│   ├── nov-2020-office-2
│   ├── nov-2020-office-3
│   ├── nov-2020-office365
│   ├── nov-2020-office-4
│   ├── nov-2020-office-5
│   ├── nov-2020-one-drive
│   ├── nov-2020-one-drive-2
│   ├── nov-2020-one-drive-3
│   ├── nov-2020-one-drive-4
│   ├── nov-2020-one-drive-5
│   ├── nov-2020-outlook
│   ├── nov-2020-outlook-2
│   ├── nov-2020-outlook-3
│   ├── nov-2020-owa
│   ├── nov-2020-owa-2
│   ├── nov-2020-sharepoint
│   ├── oct-2018-hotmail
│   ├── oct-2018-hotmail-2
│   ├── oct-2018-hotmail-3
│   ├── oct-2018-office
│   ├── oct-2018-office-2
│   ├── oct-2018-office-3
│   ├── oct-2018-office-4
│   ├── oct-2018-office-5
│   ├── oct-2018-office-6
│   ├── oct-2018-office-7
│   ├── oct-2018-office-8
│   ├── oct-2018-onedrive
│   └── oct-2019-sharepoint
├── MWeb
│   └── nov-2020-mweb
├── namecheap
│   └── sept-2020-namecheap
├── NatWest
│   └── nov-2020-natwest
├── Navy_Federal
│   └── aug-2019-navyfederal
├── NedBank
│   ├── nov-2020-nedbank
│   └── nov-2020-nedbank-2
├── Netflix
│   ├── dec-2020-netflix
│   ├── may-2020-netflix
│   ├── nov-2019-netflix
│   ├── nov-2019-netflix-2
│   ├── nov-2019-netflix-3
│   ├── nov-2020-netflix
│   ├── nov-2020-netflix-2
│   └── nov-2020-netflix-3
├── Norway
│   └── nov-2020-norway
├── Optimum
│   └── nov-2020-optimum
├── Orange
│   └── nov-2020-orange
├── OurTime
│   ├── nov-2018-ourtime
│   ├── nov-2020-ourtime
│   └── oct-2018-ourtime
├── PayPal
│   ├── aug-2019-paypal
│   ├── aug-2019-paypal-validator
│   ├── dec-2019-paypal
│   ├── july-2020-monstronix-paypal
│   ├── july-2020-xfreak-paypal
│   ├── july-2020-xhunter-paypal
│   ├── june-2019-XBanana-PayPal
│   ├── june-2020-paypal
│   ├── june-2020-paypal-2
│   ├── nov-2019-paypal
│   ├── nov-2019-paypal-2
│   ├── nov-2019-paypal-3
│   ├── nov-2020-paypal
│   ├── nov-2020-paypal-2
│   ├── oct-2018-paypal
│   ├── oct-2018-paypal-2
│   ├── sept-2019-paypal
│   └── sept-2020-paypal
├── PNB_Bank
│   └── dec-2020-pnb-bank
├── PNC
│   ├── oct-2018-pnc
│   └── oct-2019-pnc
├── Postal_Bank_FR
│   └── nov-2020-postal-bank
├── Protonmail
│   ├── feb-2020-protonmail
│   └── march-2020-protonmail
├── PUBG
│   ├── sept-2020-pubg
│   ├── sept-2020-pubg-2
│   ├── sept-2020-pubg-3
│   ├── sept-2020-pubg-4
│   ├── sept-2020-pubg-5
│   ├── sept-2020-pubg-6
│   └── sept-2020-pubg-7
├── Rabobank
│   ├── jan-2020-rabobank
│   └── nov-2020-rabobank
├── Rackspace
│   ├── march-2020-rackspace
│   └── nov-2020-rackspace
├── Rogers
├── Royal_Bank_of_Canada
│   └── oct-2018-rbc
├── Salesforce
│   └── dec-2020-salesforce
├── Santander
│   ├── nov-2020-santander
│   └── sept-2020-santander
├── SFExpress
│   └── nov-2020-SFExpress
├── SFR
│   ├── nov-2020-sfr
│   └── nov-2020-sfr-2
├── ShareFile
│   └── nov-2020-sharefile
├── SingNet
│   ├── nov-2020-singnet
│   └── nov-2020-singtel
├── South_State_Bank
│   └── july-2019-ssb
├── Suntrust
│   ├── july-2019-suntrust
│   └── nov-2020-suntrust
├── Swiss_Post
│   ├── nov-2020-swiss
│   └── nov-2020-swiss-2
├── Symantec
│   └── june-2019-Symantec
├── Tax-Fraud
│   └── aug-2019-france-tax-refund
├── TDAmeritrade
│   └── nov-2020-TD
├── Telus
│   └── aug-2019-telus
├── TurboTax
│   └── oct-2018-turbo-tax
├── UK_Government
│   └── nov-2020-dvla
├── Union_Bank
│   └── nov-2020-union-bank
├── University-of-Southern-California
│   └── dec-2020-usc-email
├── UPS
│   └── nov-2018-ups
├── USAA
│   └── july-2019-usaa
├── US_Department_of_Energy
│   └── march-2020-us-doe-gen-email
├── Verizon
│   ├── aug-2019-verizon
│   └── july-2019-verizon
├── VMware
│   └── Zimbra
├── WellsFargo
│   ├── aug-2019-wells-fargo
│   ├── june-2019-wells-fargo
│   ├── june-2020-wells-fargo
│   ├── may-2020-wells-fargo
│   ├── may-2020-wells-fargo-2
│   ├── nov-2020-wells-fargo
│   ├── nov-2020-wells-fargo-2
│   ├── nov-2020-wells-fargo-3
│   ├── nov-2020-wells-fargo-4
│   ├── oct-2018-wells-fargo
│   ├── oct-2018-wells-fargo-2
│   └── oct-2020-wells-fargo
├── West_Pac_Country
│   └── nov-2020-westpac
├── WeTransfer
│   ├── dec-2019-wetransfer
│   ├── july-2019-wetransfer
│   ├── nov-2020-wetransfer
│   └── nov-2020-wetransfer-2
├── WhatsApp
│   ├── june-2020-whatsapp
│   └── may-2020-whatsapp
├── Xerox
│   └── march-2020-xerox
├── Yahoo
│   ├── feb-2020-yahoo
│   ├── jan-2020-yahoo
│   ├── march-2020-yahoo
│   ├── may-2020-yahoo
│   └── nov-2020-yahoo
├── Zimbra
│   ├── dec-2020-zimbra
│   ├── nov-2020-zimbra
│   └── nov-2020-zimbra-2
├── Ziraat
│   └── dec-2019-ziraat
├── Zoom
│   ├── may-2020-zoom
│   └── may-2020-zoom-2
└── Zoosk
    └── oct-2018-zoosk

469 directories
```
