---
id: 472
title: 'How to &#8211; Fix MySQL Command line Client crashing problem.'
date: '2018-01-07T09:59:28+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=472'
permalink: /2018/01/07/how-to-fix-mysql-command-line-crashing-problem/
image: /wp-content/uploads/2018/01/1200px-mysql-svg.png
categories:
    - Windows
---

MySQL is one of the popular and open-source Relational databases available in the market. And it supports connectivity for all popular programming languages including C++, JAVA, and C#.

We can install the MySQL server on our machine by simply downloading the setup binaries from the [official site](https://www.mysql.com/downloads/) and installing it just like we install any other software. While installing setup will prompt you for the root password for the security of the database access.

![MySQL command line client](https://mccshreyas.files.wordpress.com/2018/01/screenshot-85.png?resize=396%2C603)

After installing it successfully, you can now create and manage the MySQL database by opening the MySQL command-line client. But I found many users on the internet that are complaining about MySQL command-line client crashes after they typed the ‘correct’ root password.

Some days ago my machine also ran into the same problem. When I started to look into it in order to fix the issue, I found the main root cause of it. The problem was the *MySQL service was disabled somehow in the background*. That’s why although we typed the correct password, the MySQL command-line client was not able to contact its service to give access to the MySQL shell and because of that, it was crashing again and again. So if you are facing the same issue then this post is meant for you. Following are the simple steps that you should follow in order to fix the issue. So let’s get started…….

## **Steps**

1. Press the Windows logo key + R simultaneously to open the ‘Run’ dialog box
2. In the ‘Run’ dialog box type **services.msc** and hit enter to open the Services window. ![Services.msc](https://mccshreyas.files.wordpress.com/2018/01/screenshot-86.png?resize=400%2C205)
3. In the services window, search for *MySQL57* service and double click on it to open.![MySQL service](https://mccshreyas.files.wordpress.com/2018/01/screenshot-87.png?resize=700%2C397)
4. You will notice that the service is either disabled (in startup type) or stopped in service status.
5. Select Automatic or Automatic (Delayed start) in the select box of Startup type and click on apply. So that whenever your machine starts the MySQL service will start automatically in the background.![Screenshot (88)](https://mccshreyas.files.wordpress.com/2018/01/screenshot-88.png?resize=700%2C394)
6. After that click on Start button to start the MySQL service on your machine. It will take some few seconds to start (wait is worth). Then click on apply and hit Ok. Then close the services window also.![Screenshot (89)](https://mccshreyas.files.wordpress.com/2018/01/screenshot-89.png?resize=700%2C394)

Now try to open MySQL command-line client, enter the correct root password when prompted and hit enter. The MySQL shell will start without any issues and you will be able to manage your databases.

## How to – Check MySQL service status

You can also check whether the MySQL service is running in the background or not. To do that open Task manager ( Press CTRL + SHIFT + ESC simultaneously ) and look for mysqld service in the background process section. If it isn’t listed there then the service is stopped or disabled. You have to follow the same previous step to start it again.

![Task manager MySQL service](https://mccshreyas.files.wordpress.com/2018/01/screenshot-91.png?resize=700%2C506)

So in this way, we can fix the crashing issue my MySQL command line client. The above steps are applicable to Windows 10/8.1/8/7. If you face any problem while performing steps make sure you hit a comment in the comment section below.

Cheers…