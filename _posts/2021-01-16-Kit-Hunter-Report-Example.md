---
layout: default
categories: khdocs
title: A quick Kit Hunter report example
date: 2021-01-16
description: As work continues on Kit Hunter, I felt it might be worth sharing an example report, and go over what it represents, as well as the various elements within.
image: /images/code.png
---

(Updated 2021-09-26)

To start with, Kit Hunter is a contextual search tool that can be used on any system that supports Python 3.

It was created to assist administrators with the task of detecting and removing phishing kits from their websites / webservers. This is especially useful in shared-hosting environments where an administrator would need to search multiple directories. However, it also has useful applications for single domain managers, as well as researchers investigating phishing kits. Something I'll explore in later posts.

## An easy to follow report

It might not be the prettiest report, but it is a useful report. As work continues on Kit Hunter, I felt it might be worth sharing an example report. The example will go over what the report represents, as well as the various elements within. As mentioned above, this blog post was updated in September of 2021. The example scan focused on an Apple phishing kit hidden within a basic WordPress website.

## Scan Area:

The first line of the report shows the folder or archive that was scanned, as well as its exact location on the server.

>Note: In the examples below, `/public_html/wp-content/themes/twentysixteen/inc` were removed for visibility.

```
| ==============================================================================
| Folder Scanned:
|
| /1b097f33650d310d0aa8ba09a6c5351a/
|
```

## Files Flagged:

The second line lists the files that were detected as suspect during the scan. These files contain known tags, or known indicators, which usually point to the existence of a phishing kit. Context is key. The administrator should already have a good idea of what files are on the server. This type of listing should immediately raise red flags if the files or directories are unknown. However, because criminals routinely hijack websites, even "known" files could be problematic. In the example below, the callout to "`Apple_Login.php`" is an immediate red flag, as is the existence of a `success.php` file in the same directory.

```
| ==============================================================================
| The following files contain known phishing keywords:
| ==============================================================================
|
| File: '/1b097f33650d310d0aa8ba09a6c5351a/.htaccess'
| File: '/1b097f33650d310d0aa8ba09a6c5351a/Apple_Login.php'
| File: '/1b097f33650d310d0aa8ba09a6c5351a/index.php'
| File: '/1b097f33650d310d0aa8ba09a6c5351a/login.php'
| File: '/1b097f33650d310d0aa8ba09a6c5351a/sayron.php'
| File: '/1b097f33650d310d0aa8ba09a6c5351a/success.php'
| File: '/1b097f33650d310d0aa8ba09a6c5351a/updateinformation.php'
|
```

## Tags Detected:

The third area shows the tags that were detected by the scan. In Kit Hunter, tags are elements that have been observed during active phishing attacks.

Tags can include script functions, application calls, names of kit authors, email domains, brands, etc. In the example below, you see several brands being abused, security mechanisms, a function call, and detections by the Apple Phishing rule.

### Security Indicators

When Kit Hunter flags on security indicators, this means it has detected something criminals often use to keep their kits hidden from detection, or to help keep their kits from being abused. In the example below `$blocked_words = array(`is a function that is often used to prevent junk form submissions, or to prevent access based on browser or header information. Another tag below (`HTTrack`) has a duel use, as it is often blocked to prevent the kit from being stolen, or it is detected because criminals will copy their victim brand's website wholesale. The other tags are names of known security vendors or bots, which are frequently blocked by phishing kits. Likewise, Tor is blocked as it is seen as a security risk by phishing kit developers.

```
| ==============================================================================
| The following tag file reported matches: Phishing_Kit_Security_Indicators.tag
| ==============================================================================
|
|           Tag: '$blocked_words = array('
|           Tag: 'HTTrack'
|           Tag: 'calyxinstitute'
|           Tag: 'cyveillance'
|           Tag: 'dreamhost'
|           Tag: 'safebrowsing-cache'
|           Tag: 'softlayer'
|           Tag: 'tor-exit'
|
```

### Brand Indicators

The brand indicators in Kit Hunter are there to help assist in contextual awareness. In this case, there are several calls to Apple based services, which isn't likely to be normal on domains that aren't focused on Apple. Likewise, the URL indicators are there to show possible issues. In this example, the issues include the fact that assets are being called on from Apple. Again, something to be investigated.

```
| ==============================================================================
| The following tag file reported matches: Phishing_Kit_Brand_Indicators.tag
| ==============================================================================
|
|           Tag: 'Apple'
|           Tag: 'Microsoft'
|           Tag: 'iCloud'
|           Tag: 'iForgot'
|           Tag: 'iTunes'
|
| ==============================================================================
| The following tag file reported matches: Phishing_Kit_URL_Indicators.tag
| ==============================================================================
|
|           Tag: 'apple.com'
|           Tag: 'iforgot.apple.com'
|           Tag: 'paypal.com'
|
```
### Detection Rules

Named detection rules in Kit Hunter exist because multiple URLs, functions, author names, brands, etc. have been observed during testing and phishing kit processing, which warranted a single detection ruleset. In the example below, the tags that are being called out have been seen in multiple Apple phishing kits, and should be inspected immediately.

```
| ==============================================================================
| The following tag file reported matches: Apple_Phishing_Detection.tag
| ==============================================================================
|
|           Tag: 'appleid.cdn-apple.com'
|           Tag: 'omni_page'
|
| ==============================================================================
| The following tag file reported matches: Phishing_Kit_Function_Indicators.tag
| ==============================================================================
|
|           Tag: 'geoplugin'
|
```

### The exact matching lines of code from the detection

Finally, the last section is what offers additional context. It shows the exact line where the tag is being used. There is a character limit, which exists to prevent the report log from being filled up due to various phishing kit development practices.

However, even with the limits, it should provide enough at-a-glace context to determine if the flagged file is something that needs to be removed, or investigated further. For example, there are many files in legitimate WordPress installs that might trigger on some of the function and brand tags, however, this section of the report will provide enough context to show their risk level.

For this post, I'm only listing a few of the lines that were returned in the report, just to give some idea of what it looks like.

```
| ==============================================================================
| The following lines contained the previously flagged phishing tags:
| ==============================================================================
|
| Line:  '<meta http-equiv="refresh" content="3;url=hxxp://www.apple.com/" />'
| Line:  '<meta name="Author" content="Apple Inc.">'
| Line:  '<meta name="Description" content="Your Apple ID is the account you
| Line:  '<meta name="Title" content="Apple ID">'
| Line:  '<meta name="keywords" content="Apple ID, Sign In, Account, Password, Manage">'
| Line:  '<meta name="omni_page" content="Apple - My Apple ID">'
| Line:  "        $bname = 'Apple Safari';"
| Line:  'RewriteCond %{HTTP_USER_AGENT} HTTrack [NC,OR] '
| Line:  '[~]================== Apple Account ==================[~]<br />'
| Line:  '[~]================== Apple Login ==================[~]<br />'
| Line:  'Copyright &copy; 2016 Apple Inc. All rights reserved.'
| Line:  '<div class="title pull-left">Apple&nbsp;ID</div>'
| Line:  '<h1>Confirm Your Apple&nbsp;ID</h1>'
| Line:  'deny from apple.com'
| Line:  'deny from paypal.com'
| Line:  '|Apple ID = <b><font color=\'green\'>".$_SESSION[\'Eamil\']."</font></b><br />'
| Line:  "|Apple ID = <b><font color='green'>$Eamil</font></b><br />"
| Line:  "|Apple Password = <b><font color='green'>$Password</font></b><br />"
| Line:  '<img src="hxxps://appleid[.]cdn-apple[.]com/static/bin/cb3498496948/ [redacted]"
| Line:  '<a href="{{iForgotLinkUrl}}" role="link">Forgot Apple ID or password?</a>'
|
```
