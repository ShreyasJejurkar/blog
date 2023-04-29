---
id: 198
title: 'How to Reinstall Microsoft Edge on Windows 10. /Solve Microsoft Edge crashing issue.'
date: 2015-12-14T10:24:09+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=198'
slug: how-to-reinstall-microsoft-edge-on-windows-10
categories:
    - Windows
---

[  
 ![](http://mccshreyas.files.wordpress.com/2015/12/savedpicture-20151214172844.jpg?w=700)  ](http://mccshreyas.files.wordpress.com/2015/12/savedpicture-20151214172844.jpg)  
As I am one of the contributor([Shreyas02](http://answers.microsoft.com/en-us/profile/6f20ba9e-cb92-4272-b681-c6d7975ad4d4#user-profile-tab-profile)) at [Microsoft Community](http://answers.microsoft.com), I have seen so many users are facing problem with [Microsoft Edge](https://www.microsoft.com/en-us/windows/microsoft-edge).  
Most of the user’s problem are this.  
• Microsoft Edge doesn’t not open although if they click on tile.  
• Microsoft Edge is missing.  
And if you are facing this issue then this post is only for you to solve the problem.  
As Windows 10 comes with Microsoft Edge browser. It’s not an easy task to reinstall Edge as like we reinstall other programs directly. There is another way to do that. We have to Re-register the Microsoft Edge browser and then reinstall it.  
So just follow the steps given below and get back that new generation browser Microsoft Edge.  
1\. Press **Windows logo key + Q**. In that search box type “PowerShell” (without quotes). After PowerShell shows in search result, right click on that and click on “Run as administrative”.  
2\. After PowerShell open type following command in that.

> Get-AppXPackage -AllUsers -Name Microsoft.MicrosoftEdge | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register “$($\_.InstallLocation)\\AppXManifest.xml” -Verbose}

  
3\. After typing full command just hit enter. <u>This command will re-register and reinstall Microsoft Edge on your PC. </u>  
4\. Just reboot the PC to take effect. And then open Microsoft Edge. Done.

If you’re facing any problems while doing this, then hit comment below.