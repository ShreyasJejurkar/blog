---
id: 312
title: 'How to - Solve Team explorer fatal error during Visual Studio installation'
date: 2016-09-11T08:21:12+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=312'
slug: how-to-solve-team-explorer-fatal-error-during-visual-studio-installation
publicize_twitter_user:
    - MCCshreyas
categories:
    - Downloads
    - Windows
---

Recently I started developing [Universal Windows Platform (UWP) ](https://msdn.microsoft.com/en-us/windows/uwp/get-started/whats-a-uwp)apps for Windows 10 devices, a jump from WPF -&gt; UWP. And my experience with that is just great. Just code once and deploy it on multiple (Windows 10) devices without changing a single line of code (and that’s what today’s developer needs). But the way for me was not so simple. For over two days I was finding the way to troubleshoot the fatal error of Visual Studio 2015 community edition. While configuring VS2015 for UWP apps development the Team Explorer fatal error keeps coming and making an obstacle for installation. I binged, googled it many times for solution but the result was zero. But with following steps I managed to troubleshoot that fatal error. I have seen many people are frustrated with the same problem. So in my today’s post, I am going to tell the troubleshooting step that you should perform to solve the problem.

**Steps**  
1\. **Clean up temporary files**  
For that press Windows logo key + R. ‘Run’ window will come up and in that text box type ‘%temp%’ (without quotes) and hit enter.  
[  
![](http://mccshreyas.files.wordpress.com/2016/09/savedpicture-2016911135610.png?w=700)  ](http://mccshreyas.files.wordpress.com/2016/09/savedpicture-2016911135610.png)  
The Explorer will navigate you to ‘temp’ (temporary files) folder. In that folder select all files (Ctrl + A) and delete them. [  
![](http://mccshreyas.files.wordpress.com/2016/09/savedpicture-2016911135615.png?w=700)  ](http://mccshreyas.files.wordpress.com/2016/09/savedpicture-2016911135615.png)

2\. **Repair the registry**   
To do that you can use [RegCure Pro tool](http://www.paretologic.com/products/regcurepro/) or [Registry Cleaner from Advance system care ](http://www.iobit.com/en/advancedsystemcarefree.php)and run the tool. After you, open Registry Cleaner tool at the bottom check the box of Deep clean and click on scan. That will scan your registry files and will find errors. After scan completed select all error and click on fix it button at the top.

After you done all these above steps Re-run the visual studio setup and try to install it. It will work like a charm. If you any doubt or any problem while doing this, you can ask me in the comment section below.  
Let me know is your problem solved