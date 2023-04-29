---
id: 320
title: 'Enable F8 Key Safe Mode For Troubleshooting in Windows 10'
date: 2016-12-20T15:26:30+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=320'
slug: enable-f8-key-safe-mode-for-troubleshooting-in-windows-10
publicize_twitter_user:
    - MCCshreyas
categories:
    - Windows
---

With Windows 10, Microsoft has improved the logic behind the booting of OS much more, making it faster than ever before. From my personal experience, my system boots only in 5 seconds although I have 13 application in the start-up.  
But on another side, Microsoft removed the easy way to enter into safe mode on Windows 10. With Windows 7 we can easily boot into Windows safe mode at the start by rapidly pressing the F8 key as soon as BIOS loads. This key acts like the lifesaver for those whose system gets locked in continuous restart due to some malware or installing some unsupported drivers. But there is an easy way to again enable this F8 key for troubleshooting in Windows 10. So the following guide will help you to enable that.  
Follow the steps.  
1\. Press **Windows Logo key + X** simultaneously. As soon as you press, the menu will pop-up from lower left corner called as ‘Power user menu’.  
[  
![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-2016122021016.png?w=700)  ](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-2016122021016.png)  
2\. In that click on ‘Command Prompt (Admin)’ to open it.  
3\. After that type following command carefully in CMD

> bcdedit /set {default} bootmenupolicy legacy

[  
![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-2016122021024.png?w=700)  ](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-2016122021024.png)  
4\. And hit enter. If you type that command correctly you will receive the message like this **The operation completed successfully**.  
[  
![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-2016122021032.png?w=700)  ](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-2016122021032.png)  
And done. You have just enabled the F8 key for troubleshooting in Windows 10. Just restart the system. And as soon as your PC starts rapidly press F8 key on the keyboard. And you will see the ‘Safe Mode’ menu on the screen. And from there you can easily boot into Safe mode and can easily troubleshoot your problem from there.  
If you face any problem doing this, make sure that you hit comment below.