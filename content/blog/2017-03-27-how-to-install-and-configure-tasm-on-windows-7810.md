---
id: 412
title: "How to install and configure TASM on Windows 7/8/10.\_"
date: 2017-03-27T05:19:22+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=412'
slug: how-to-install-and-configure-tasm-on-windows-7810
publicize_twitter_user:
    - MCCshreyas
image: /wp-content/uploads/2017/03/wp-1490591761960.png
categories:
    - Downloads
    - Windows
---

Before we get started with TASM installation on a Windows machine, let’s get some knowledge about TASM and learn what it will do for us.

> Turbo Assembler (TASM) a small 16-bit computer program which enables us to write 16 bit i.e. x86 programming code on 32-bit machine. It can be used with any high level language compliers like GCC compiler set to build object files. So that programmers can use their daily routine machines to write 16-bit code and execute on x86 devices.

So let get started with installation steps. Before we get started to make sure that you have the following software. If not, you can download it by clicking on it.

**Requirements**.

1\. [DosBox software.](http://www.dosbox.com/download.php?main=1)

2\. [TASM installation files](https://drive.google.com/file/d/0BxFfQqBvZCltMHdNbFFCZVJkUlE/view?usp=sharing).  
 **Steps**

1\. First, install DOSBox software on your system.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591369444.png?resize=460%2C311)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591369444.png?resize=460%2C311)

2\. Just run the downloaded setup file to install as just like other software you install.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591399488.png?resize=549%2C478)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591399488.png?resize=549%2C478)

3\. Then extract the TASM zip file.

4\. After that copy that extracted the folder to C drive of your system.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591426342.png?resize=700%2C394)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591426342.png?resize=700%2C394)

5\. Now we have to mount our C drive to DosBox so that we can use our TASM libraries there.

6\. To do that go to the following path on your PC

> **For 32-bit PC**
> 
> C:\\Program Files\\DOSBOX-0.74
> 
> **For 64-bit PC**
> 
> C:\\Program Files (x86) \\DOSBOX-0.74

7\. Then there you will see a file named “DOSBOX 0.74 Options” click on it to open.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591556492.png?resize=700%2C394)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591556492.png?resize=700%2C394)

8\. It will open a text file in notepad. Then navigate to the last line of that file where it shows “# You can put your MOUNT lines here”.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591592589.png?resize=700%2C394)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591592589.png?resize=700%2C394)

9\. Add the following lines after that.

> mount c c://tasm
> 
> c://

10\. And save that file.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591602464.png?resize=700%2C394)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591602464.png?resize=700%2C394)

11\. And now open DOSBOX. You’re done.  
12\. To run a TASM program copy your program file into the TASM folder which is under your C: drive.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591694938.png?resize=700%2C394)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591694938.png?resize=700%2C394)

13\. And now open DOSBOX. And navigate to the TASM folder by typing *cd TASM* and hit enter.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591746100.png?resize=700%2C370)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591746100.png?resize=700%2C370)

14\. Now type tasm &lt;program\_name&gt;. Replace &lt;program\_name&gt; with your actual program name. in my case, my program name is the timer so I will type tasm timer.asm

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591761960.png?resize=700%2C373)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591761960.png?resize=700%2C373)

15\. After you hit enter. You will see an error, warning messages. If there isn’t anything wrong with your program syntactically, you will see none there.

[![](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591792111.png?resize=700%2C373)](http://mccshreyas.files.wordpress.com/2017/03/wp-1490591792111.png?resize=700%2C373)

16\. And now link your program to that type *tlink &lt;program\_name&gt;* and hit enter. And now execute program by typing &lt;program\_name&gt; only.  
17\. The program will start executing. To stop execution type exit and hit enter.

So in this way you can install TASM on your system and execute x86 code on your machine. This tutorial is applicable to Windows 7/8/8.1/10.

If you face any problem while doing this, make sure that you hit the comment below with your problem.

[via](https://drive.google.com/file/d/0BxFfQqBvZCltMHdNbFFCZVJkUlE/view?usp=sharing)