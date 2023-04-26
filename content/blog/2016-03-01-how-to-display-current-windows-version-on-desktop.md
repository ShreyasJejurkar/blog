---
id: 242
title: 'How to &#8211; Display Current Windows Version On Desktop'
date: '2016-03-01T17:29:23+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=242'
permalink: /2016/03/01/how-to-display-current-windows-version-on-desktop/
publicize_google_plus_url:
    - 'https://plus.google.com/109457878009607673055/posts/FHnEXymDSxE'
publicize_twitter_user:
    - MCCshreyas
categories:
    - Windows
---

Earlier version of Windows Operating system was able to show version number at the bottom of the home screen (more specifically on desktop). But that feature is removed by Microsoft in latest version of Windows.  
But today I am going to tell you one of the trick by which you can enable that again, whatever version of Windows are you using. This is just simple registry hack which will able to do that.

**Follow the steps**  
1\. Navigate to following path in registry.

> \[HKEY\_CURRENT\_USER\\Control Panel\\Desktop\]

2\. Right clicking on it, create a new DWORD value. Or you edit the **‘PaintDesktopVersion’** key and changing it value to 1.

Then close the registry and restart the computer to take effect. And after start up you will notice that the current Windows version will show up there at the bottom of desktop.  
Isn’t it interesting??  
Try Now..