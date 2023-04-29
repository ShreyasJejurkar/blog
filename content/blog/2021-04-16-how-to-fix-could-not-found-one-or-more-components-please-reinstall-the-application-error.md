---
id: 595
title: 'How to fix - Could not found one or more components. please reinstall the application error.'
date: 2021-04-16T17:08:12+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=595'
slug: how-to-fix-could-not-found-one-or-more-components-please-reinstall-the-application-error
timeline_notification:
    - '1618573095'
publicize_linkedin_url:
    - ''
image: /wp-content/uploads/2021/04/sql-server-1.png
categories:
    - Programming
    - Windows
tags:
    - 'sql server 2014'
    - 'Visual Studio 2010'
---

Recently I was working on one of the projects where I was using SQL Server 2014 as a database and Visual Studio 2019. And suddenly I started getting the above error when I tried to open SQL Server 2014. I tried repairing the installation of SQL Server 2014 via the installer, but it did not work, and I was getting the same error as before.

So I got into thinking, like what I did before I was getting this error, then I realized that I have deleted the “Visual Studio 2010” folder from my Program Files (x86) folder. Because I was not using Visual Studio 2010, I was using the 2019 edition so technically, I don’t need that folder and its corresponding files to work, so to get some free space I deleted those folders and this is where I made the mistake.

So after some research, I found that Visual Studio 2014 behind the scenes uses Visual Studio 2010 UI components for its rendering and its controls. That’s why if you compare the “Solution Explorer” UI from Visual Studio 2010, then it looks somewhat similar to “Object Explorer” in SQL Server 2014. Because they are the same under the hood and only the content is different.

So does that mean to work with SQL Server 2014 I need to install Visual Studio 2010 although if I am not using it !? No, the UI (“UI Shell”) is a separate component from Visual Studio and SQL Server. As part of their installation, they install this component. And interestingly as it packs separately from these products so we can separately download that as well and install it. The component name is **Visual Studio Isolated Shell**.

You can download the shell from the below link.

<https://visualstudio.microsoft.com/vs/older-downloads/isolated-shell/>

But on that page when you accept a license, you will see a different version of that shell ranging from Visual Studio 2010 to 2015. So this is where we need to make the decision, and the following list might help to make that.

1\. SQL Server 2014 -&gt; Visual Studio 2010 isolated shell.   
2\. SQL Server 2016 -&gt; Visual Studio 2015 isolated shell.

So make sure to install the correct shell, and give it a try to open SQL Server. In my case, it worked, but in your case, if it didn’t, then after installation of shell, repair the SQL Server installation and try again that will really help and will eventually solve your problem.   
  
Thanks for reading..!