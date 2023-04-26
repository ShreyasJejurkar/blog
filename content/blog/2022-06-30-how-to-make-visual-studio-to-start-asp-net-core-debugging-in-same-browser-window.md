---
id: 853
title: 'How to make Visual Studio to start ASP.NET Core debugging in same browser window'
date: '2022-06-30T15:14:26+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://shreyasjejurkar.com/?p=853'
permalink: /2022/06/30/how-to-make-visual-studio-to-start-asp-net-core-debugging-in-same-browser-window/
categories:
    - Programming
tags:
    - aspnetcore
    - 'visualstudio C#'
---

If you are working with ASP.NET or ASP.NET Core projects in Visual Studio for developing web applications, then you might have come across this wired issue in Visual Studio.

The issue is whenever you start a debugging session (F5) inside Visual Studio for web projects, it always opens a new browser window (maybe chrome/edge based on your default preferences) for each debugging session. I don’t think that’s a good experience, because most of us developers have an already open browser window that actually opens most of the time to search for bug fixes or create PR to GitHub or Azure DevOps. So having 2 separate browser windows puts a lot of pressure on RAM. And also it’s not like the chrome opens faster each time, every time it takes some initial seconds to open and then load the actual project in it.

So in this blog post, I will let you know the steps needed for avoiding a new window each time and making Visual Studio actually open in a new tab inside an already open browser window.

Steps –

1. Open Visual Studio and navigate to Tools -&gt; Options.
![tools->options settings vs](https://i0.wp.com/shreyasjejurkar.com/wp-content/uploads/2022/06/vs-options.png?resize=700%2C423&ssl=1)

2. After that in the Projects and Solutions section go to Web projects. There check the checkbox which is highlighted below.
![third checkbox tick](https://i0.wp.com/shreyasjejurkar.com/wp-content/uploads/2022/06/settings-1.png?resize=700%2C489&ssl=1)

3. Then go to Debugging -&gt; General tab. And uncheck the checkbox which is highlighted below.
![debugging general settings](https://i0.wp.com/shreyasjejurkar.com/wp-content/uploads/2022/06/settings-2.png?resize=700%2C437&ssl=1)

4. And then lastly to save these changes, click on the Ok button on the window.
And that’s it. These two changes will make sure the Visual Studio will open the new debugging tab in the same browser window instead of opening new.

I hope this post helps to solve this issue. In case of any problems, please let me know in below comment section.

Thank you…