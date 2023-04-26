---
id: 286
title: 'How To &#8211; Fix Start Menu Not Working Issues in Windows 10'
date: '2016-07-25T06:42:04+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=286'
permalink: /2016/07/25/how-to-fix-start-menu-not-working-issues-in-windows-10/
publicize_twitter_user:
    - MCCshreyas
categories:
    - Windows
---

[  
![](http://mccshreyas.files.wordpress.com/2016/07/savedpicture-2016725121430.png?w=700)  ](http://mccshreyas.files.wordpress.com/2016/07/savedpicture-2016725121430.png)With Windows 10, Microsoft has brought start menu to the desktop again. It’s not fully like Windows 7 which we loved so more but also it’s not like Windows 8 start menu which we hated a lot. It’s a mixture of Windows 7 and Windows 8 start menu. Like Windows 7, the start menu is vertical and like Windows 8 we can pin the modern apps to it and can take advantage of live tiles feature. Everyone likes the design of start menu. And it also gets full screen when you switched to tablet mode in Windows 10.  
But as there are new things to enjoy, there are some bad things to care about. Many people reported that after pining bulk of apps to start menu, it starts lagging. For the bunch of people, the start menu wasn’t opening. If you are one of them, then today’s post will help you to fix that problem.  
Following steps will help you to repair start menu in Windows 10.

Steps  
1\. Type “powershell” (without quotes) at the search box at the bottom. After that right click on **Windows PowerShell** desktop app from the search result and click “Run it as administrator” option from context menu.  
2\. After that type following phrase in that. Careful while typing.

> Get-AppXPackage -AllUsers | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register “$($\_.InstallLocation)\\AppXManifest.xml”}

3\. And then hit enter. And wait. The bunch of commands will start executing. Once it gets finished restart the computer and try to launch start, it will open seamlessly.

So in this way, we can fix the issues wit the start. If you face any problem while doing this, then hit comment below about that.