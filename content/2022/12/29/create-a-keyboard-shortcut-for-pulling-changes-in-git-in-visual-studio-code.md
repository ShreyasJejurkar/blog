---
id: 873
title: 'Create a keyboard shortcut for pulling changes in git in Visual Studio Code'
date: 2022-12-29T14:48:41+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://shreyasjejurkar.com/?p=873'
permalink: /2022/12/29/create-a-keyboard-shortcut-for-pulling-changes-in-git-in-visual-studio-code/
categories:
    - Programming
---

If you are a web developer or a software engineer, it’s most likely you are using Visual Studio code as your code editor. Yeah, it’s fantastic and easy to use. But I wondered when I found that there is no default shortcut key for most used options in git workflow, which pulls changes from upstream. So I decided to have a shortcut for pulling changes from upstream for both the current branches and different branches and also I though I should write a blog post around this just to let people know how to do that. So, let’s get started….

Steps

1. Open Visual Studio Code and go to File à Preference à Keyboard shortcuts alternatively you can press CTRL + K S to open it.  
    ![](https://i0.wp.com/shreyasjejurkar.com/wp-content/uploads/2022/12/KeyboardShortcut-1.png?resize=700%2C692&ssl=1)
2. Once you open it, you will see a lot of options there. Basically, these are the various operations for which you can assign a keyboard shortcut. So instead of getting lost in all options, at the top, you will see a search bar where you can search for a particular action in our case we will type “git pull” (without quotes)  
      
    ![search git pull option ](https://i0.wp.com/shreyasjejurkar.com/wp-content/uploads/2022/12/SearchGitPull-1.png?resize=603%2C229&ssl=1)
3. Once you search that you will see the first 2 entries of “git pull” and “git pull from”. And next to it you will see an empty cell under the Key Bindings column. You can double-click on that and press the key that you want to assign for that particular operation. In my case I will assign git pull to “ALT + E” and git pull from to “CTRL + ALT + E” as you can see below.  
      
    ![shortcut assignment](https://i0.wp.com/shreyasjejurkar.com/wp-content/uploads/2022/12/ShortcutAssignment-1.png?resize=603%2C77&ssl=1)  
      
      
    So, this is all that we have to do. Now next time when you want to pull changes, instead of going the usual way, on the keyboard you can just press the shortcut key whatever you assign in the previous step.  
    I know this isn’t rocket science, but still, it saves some seconds and feels great and productive!  
    In case you face any issues while performing the above steps, please let me know in the comment section below.  
      
      
      
      
    Thanks!