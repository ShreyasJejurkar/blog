---
id: 177
title: 'How to fix- Change PC Settings Crashing.'
date: '2015-11-17T07:49:20+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=177'
permalink: /2015/11/17/how-to-fix-change-pc-settings-crashing/
categories:
    - Windows
---

Hello there. I am Shreyas. After a long time I am came back with a new **troubleshooting post about Windows 8.1.** I know Windows 10 has been launched but still I am going to tell you about 8.1  
Mostly when people upgrade from Windows 8 to Windows 8.1, they face one problem about **crashing of Change PC settings**. This happen <u>mostly when something get wrong while upgrading Windows version</u>.  
But its so easy to solve this problem.  
So follow the steps and get rid from this frustrating problem.  
1\. **Open Command Prompt** (Administrative). You can do this by pressing Windows logo key+X simultaneously and then from that short menu click on Command Prompt (administrative).  
2\. In that CMD window. Type the following command carefully.

> **powershell -ExecutionPolicy Unrestricted Add-AppxPackage -DisableDevelopmentMode -Register $Env:SystemRoot\\ImmersiveControlPanel\\AppxManifest.xml**

Actually this is a<u> Powershell command</u>. This command will repair the component of “Change PC settings”. After full command execution the CMD will return to same directory of system.  
3\. There is *no requirement of restarting PC, but I will suggest you to restart the computer once*. And then open “Change PC Settings”. You will notice the change.  
Thanks for reading. If any problem then ask in comment section below.  
Cheers……..

[  
 ![](http://mccshreyas.files.wordpress.com/2015/11/savedpicture-20151117134844.png?w=700)  ](http://mccshreyas.files.wordpress.com/2015/11/savedpicture-20151117134844.png)

[  
 ![](http://mccshreyas.files.wordpress.com/2015/11/savedpicture-20151117134849.jpg?w=700)  ](http://mccshreyas.files.wordpress.com/2015/11/savedpicture-20151117134849.jpg)