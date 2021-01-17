---
layout: default
categories: code
title: A quick Kit Hunter report example
date: 2021-01-16
description: As work continues on Kit Hunter, I felt it might be worth sharing an example report, and go over what it represents, as well as the various elements within.
image: /images/code.png
---

### An easy to follow report

It might not be the prettiest report, but it is a useful report. As work continues on Kit Hunter, I felt it might be worth sharing an example report, and go over what it represents, as well as the various elements within. To start with, Kit Hunter is a search tool, that can be used on any system that supports Python 3.

It was created to assist administrators with the task of detecting and removing phishing kits from their websites. This is especially useful in shared-hosting environments where an administrator would need to search multiple directories. However, it also has useful applications for single domain managers, as well as researchers investigating phishing kits. Something I'll explore in later posts.

>**Note:** In the lines below I have added [ ] and xx to the domain variables to prevent them from being linked or accessed. Also, while the primary structure will remain, elements and presentation of the final report might change before this release is made public.

### The area scanned

The first line of the report shows the folder or archive that was scanned, as well as its exact location on the server.

```
==============================

Folder Scanned:

/public_html/wp-content/themes/twentytwenty/office356[.]com-RD163

------------------------------
```

### The files that were detected

The second line lists the files that were detected as suspect during the scan. These files contain known tags, or known indicators that usually point to the existence of a phishing kit. Context is key, as the administrator should have a good idea of what files are on the server. This type of listing should immediately raise red flags if the files or directories are unknown. However, because criminals routinely hijack websites, even "known" files could be problematic.

```
------------------------------

The following files contain known phishing keywords:

File: '/public_html/wp-content/themes/twentytwenty/office356[.]com-RD163/index.html'
File: '/public_html/wp-content/themes/twentytwenty/office356[.]com-RD163/next.php'

------------------------------
```

### The tags that triggered the detection

The third area shows the tags that detected by the scan. In Kit Hunter, tags are elements that have been observed during active phishing attacks. Tags can include script functions, application calls, kit author tags, email domains, brands, etc. In the example below, you see the brand Office 365 being abused, the kit author's name, and two different functions, which are used to geolocate the victim.

```
------------------------------

The following known phishing keywords were discovered:

Tag: 'CrEaTeD bY VeNzA'
Tag: 'Office365'
Tag: 'geoiptool'
Tag: 'gethostbyaddr($ip)'

------------------------------
```

### The exact matching lines of code from the detection

Finally, the last section is what offers additional context. It shows the exact line where the tag is being used. There is a character limit, which exists to prevent the report log from being filled up due to various phishing kit development practices, but it should provide enough at-a-glace context to determine if the flagged file is something that needs to be removed, or investigated further. For example, there are many files in legitimate WordPress installs that might trigger on some of the function and brand tags, however, this section of the report will provide enough context to show they are harmless.

```
------------------------------

The following lines contained the previously flagged phishing tags (200 chr limit):

Line:  '\t$hostname = gethostbyaddr($ip);'
Line:  '\t$message .= "|--- hxxp://www[.]geoiptool[.]com/?IP=$ip ----\\n";'
Line:  '\t$message .= "|----------- CrEaTeD bY VeNzA --------------|\\n";'
Line:  '                    <font color="#FF0000">Office365[.]com</font> Webmail'
Line:  '                    Office365</span></font> Login'


==============================
```
A copy of the full report is below. If you have any questions or comments, feel free to reach out to me.

### The full report

```
==============================

Folder Scanned:

/public_html/wp-content/themes/twentytwenty/office356[.]com-RD163

------------------------------

The following files contain known phishing keywords:

File: '/public_html/wp-content/themes/twentytwenty/office356[.]com-RD163/index.html'
File: '/public_html/wp-content/themes/twentytwenty/office356[.]com-RD163/next.php'

------------------------------

The following known phishing keywords were discovered:

Tag: 'CrEaTeD bY VeNzA'
Tag: 'Office365'
Tag: 'geoiptool'
Tag: 'gethostbyaddr($ip)'

------------------------------

The following lines contained the previously flagged phishing tags (200 chr limit):

Line:  '\t$hostname = gethostbyaddr($ip);'
Line:  '\t$message .= "|--- hxxp://www[.]geoiptool[.]com/?IP=$ip ----\\n";'
Line:  '\t$message .= "|----------- CrEaTeD bY VeNzA --------------|\\n";'
Line:  '                    <font color="#FF0000">Office365[.]com</font> Webmail'
Line:  '                    Office365</span></font> Login'


==============================
```
