---
layout: post
title: "Oculus Rift Black-Screen[EN]"
date: 2016-12-29
description: "OS Issue"
tags: [Virtual Reality, Oculus Rift, Black-Screen]
image: /assets/img/og.jpg
comments: true
---

# **Oculus Rift Black Screen - Adjust Lenses**

## **Hello Guest!**

Some of you may have the same problem as I had regarding the Oculus Rift CV1: "Adjust your lenses" at the Oculus Setup. There is sound on the Rift **BUT NOTHING IS DISPLAYED ON THE SCREEN WTF!!!** The Oculus LED was orange or white sometimes.

At first I've tried all simple possibilities on my Windows 8.1 just to see if they could solve my problem:

+ Oculus Runtime deinstalled and reinstalled
+ Bought a DisplayPort-HDMI adapter(Didn't work)
+ Rift HDMI unplugged and replugged
+ USB driver installed
+ Installed recent NVIDIA graphics driver for my NVIDIA GTX 1060
+ Mainboard driver installed


**but without success.**

After numerous of tries I have found the solution!

I did that:

1) Navigate to **oculus-runtime** folder. It is located at Program Files --> Oculus --> Support --> oculus-runtime on my PC.

![oculus-runtime](/assets/img/oculus-runtime.jpg)

2) This folder gets accessed, when you put the Rift on your head. Inside should be an executable named **DirectDisplayConfig** which is responsible for the lauch of the Oculus display. Start **DirectDisplayConfig.exe** - A console appears in short term.

![directdisplayconfig](/assets/img/directdisplayconfig.jpg)

If this error pops up: **api-ms-win-crt-string-l1-1-0.dll is missing** then you have probably the same problem as I had.


This error message pops up, when you haven't installed the Windows driver **api-ms-win-crt-string-l1-1-0.dll**. This driver should be installed automatically with the other Windows updates but sometimes it does not have joy to be installed with others :).

## **Solution:**

Download the **api-ms-win-crt-string-l1-1-0.dll** driver:
[https://support.microsoft.com/en-us/kb/2999226](https://support.microsoft.com/en-us/kb/2999226)

After installing the driver try to put on your Rift. If it works congrats^^!
If this blog-post was helpful to you then share it to those with maybe the same problem.
I apologize for my bad English if it appers in this post.


Tags: Adjust your Lenses, Oculus Rift black screen, Oculus Rift orange led, Oculus Rift CV1 drivers, Oculus Rift display driver, Oculus Rift white led
