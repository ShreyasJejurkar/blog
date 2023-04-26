---
id: 525
title: 'How to - Disable Windows Defender on Windows 10 Home / Pro'
date: '2020-01-18T08:13:51+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=525'
permalink: /2020/01/18/how-to-disable-windows-defender-on-windows-10-home-pro/
timeline_notification:
    - '1579347900'
image: /wp-content/uploads/2020/01/defenderhighusage.png
categories:
    - Windows
---

Windows 10 comes with built-in virus protection called Windows Defender. It runs in the background and gives real-time protection to your system. Real-time protection means whenever it finds a new file in the system, for example, like when you copy a new file to the system from an external drive or download a new file from the internet, the defender will start scanning it for virus or malware before you actually open it, protecting the system from getting vulnerable and makes sure that its safe to execute.

But sometimes, when the defender has configured for schedule system scan or when you’re using a software that creates a lot of temporary files in the background for its working, the defender will start eating a lot of resources to scan those files and making the system slow and unresponsive. I personally faced this problem while using Visual Studio and Adobe XD.

Yes, there are ways to exclude those files from defender scanning, but most of the time I find myself disabling defender for that time, as it’s not recommended to disable Windows defender permanently.

So, in today’s post am going to show you how you can disable Windows Defender to get rid of unwanted scanning. If you are on Windows 10 Pro edition, it’s simple to disable defender via Group Policy editor. But in today’s post am going to show you the steps that you can follow even on Windows 10 Home (as they don’t have group policy editor) to disable WD.

The following steps are **applicable for both Windows 10 Home &amp; Pro edition**.

1. Open registry editor by typing ‘regedit’ in the search box.
2. Then navigate to the following path under the registry.

> HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows Defender

![Screenshot (26)](https://mccshreyas.files.wordpress.com/2020/01/screenshot-26.png?resize=700%2C591)

3. On the right panel, right-click on-screen and create a new DWORD (32 bit) value. **New &gt; DWORD (32 bit) value**.

![Screenshot (29).png](https://mccshreyas.files.wordpress.com/2020/01/screenshot-29.png?resize=700%2C356)

3. And create a new key with this text **DisableAntiSpyware** and change its value to 1.

![Screenshot (28)](https://mccshreyas.files.wordpress.com/2020/01/screenshot-28.png?resize=700%2C372)

What this will do is, the Windows defender will read this key at start-up and as its value is 1 means true, the defender won’t start, and it will get disabled. **Make sure you restart the system to get these steps working for you**. And in case if you need to enable Windows defender again, then change the key (**DisableAntiSpyware**) value to **0.**

If you face any problem while performing the above steps, then make sure you put a comment below so that I can help you.