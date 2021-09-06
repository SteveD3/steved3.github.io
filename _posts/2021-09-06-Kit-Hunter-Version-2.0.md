---
layout: default
categories: code
title: Kit Hunter Version 2.0
date: 2021-09-06
description: Work on Kit Hunter 2.0 is almost complete.
image: /images/kit-hunter2.jpg
---
### Kit Hunter 2.0 is almost done!

It's been a while since I updated this blog.

I felt it was time to hop on and update anyone who happens to be reading about the status of my Python experiment. As the title says, Kit Hunter v2.0 is almost done. The script is in its final stages, but there is some cleanup and documentation I want to work on before I release it. Honestly, it's almost a completely different script compared to v1.0, which was released late last year.

This version of the script was mostly done shortly after the last version was released, but I kept adding little things and fixing minor bugs. I've used this script all year long as part of my ongoing phishing research, and it has helped me tremendously.

You may have seen me on CBS News this spring, [talking about unemployment phishing scams targeting people in New York](https://www.cbsnews.com/news/phishing-scam-targeted-unemployed-new-yorkers-during-pandemic/). The truth is, Kit Hunter was a large part of that story, as it helped me identify the how and why of the technical elements in the scam. Also, the phishing kit in question was just one of dozens that I downloaded that week, if not for Kit Hunter, I might have overlooked it.

### What's New?
As you can see in the header image, I've implemented a switching mechanism that offers a few options, as well as a general help file. This is one of the main changes, but there are others.
In no particular order, here are some of new features in version 2.0:

1. You can scan folders or archives (.zip, .tar, .rar, .gz), this is a major improvement compared to version 1.0, and one I am pleased is working so smoothly.

2. Scanning speeds have increased, but they are really noticeable during custom scans.

3. As mentioned, you can now run custom scans for certain tags. You can also use the custom scan option to scan with one of the tag files that ships with Kit Hunter.

4. There is a quick scan option, which takes a basic set of tags and keeps them in a single file. It won't detect everything, but it will detect most common phishing kits.

5. You can scan custom directories, without having to copy Kit Hunter into the folder to be scanned.

6. Finally, there are (at the time this was written) 41 tag files shipping with Kit Hunter. These tag files detect targeted phishing campaigns, as well as various types of phishing tricks such as obfuscation, templating, theming, and even branded kits like Kr3pto and Ex-Robotos.

As mentioned, there are 41 tag files for scanning, which will be housed in their own folder. These tag files are detected by name, and offer an at-a-glance general idea as to the nature of the results. As an example, here is a look at a report after scanning an archive. Kit Hunter still identifies the files that contain the suspect code detected by the script, but now it breaks down what type of detection happened. In this example, the code hit on multiple tag rules in the archive, including LogoKit detections, Kit Author, Brand, and setup. 

Incidentally, this scan used the -l switch, which removes the section of the report that shows matching lines, which is why they are not in the image.

![An Office 365 phishing kit was detected after the archive was scanned by Kit Hunter 2.0][img1]

My plan is to update this blog with various documentation articles and explainers for Kit Hunter 2.0 over the coming weeks. Once that is done, I will release the code on GitHub. From there, development will mostly focus on keeping the tag files updated and maintained, as well as researching the code needed for version 3.0.

[img1]:https://steved3.io/images/posts/kit_hunter_example.jpg
