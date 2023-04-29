---
id: 192
title: 'Open Command Prompt From Right Click.'
date: 2015-11-24T11:46:39+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=192'
slug: open-command-prompt-from-right-click
categories:
    - Windows
---

Hello there. I am Shreyas. And today I will tell you one of my favourite hack. By this hack you can open Command Prompt from your right click in file explorer.  
So just follow the steps and refer screenshot for help.  
1\. Open the Windows Registry editor. If you don’t know how to open, then follow the steps.  
 Press Windows logo key + R. The run dialog box will be open. Type

> regedit

 in that and hit enter. Done it will open the Windows registry editor.  
2\. Now navigate to this path

> HKEY\_LOCAL\_MACHINE\\Software\\Classes\\Folder\\Shell

Now right click on shell and create a new key called **Open in Command Prompt**   
[  
 ![](http://mccshreyas.files.wordpress.com/2015/11/savedpicture-2015112417196.png?w=700)  ](http://mccshreyas.files.wordpress.com/2015/11/savedpicture-2015112417196.png)  
Under that new key create a new key again called **Command**.  
And set it default value to this

> Cmd.exe /k pushd %L

This value will launch Command prompt.  
Save that. Done  
And now go to file explorer, right click any file you will see their option of “Open in Command Prompt.  
Done.

[  
 ![](http://mccshreyas.files.wordpress.com/2015/11/savedpicture-20151124172256.jpg?w=700)  ](http://mccshreyas.files.wordpress.com/2015/11/savedpicture-20151124172256.jpg)