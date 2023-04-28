---
id: 424
title: "How to &#8211; Do C/C++ graphics program in Ubuntu // install libgraph (graphics.h) in Ubuntu."
date: 2017-04-09T09:03:09+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/2017/04/09/how-to-cc-graphics-program-in-ubuntu-install-libgraph-graphics-h-in-ubuntu/'
permalink: /2017/04/09/how-to-cc-graphics-program-in-ubuntu-install-libgraph-graphics-h-in-ubuntu/
publicize_twitter_user:
    - MCCshreyas
categories:
    - Ubuntu
---

In my last post under the category of [Ubuntu](https://googleweblight.com/i?u=https://mccshreyas.wordpress.com/category/ubuntu/&hl=en-IN), I have shown you how you can easily [setup Ubuntu as VM (virtual machine) under VirtualBox](https://mccshreyas.wordpress.com/2017/01/22/396/&hl=en-IN). And today we are going to talk about installing libgraph (graphics.h) in Ubuntu.

Linux is very popular in the world of developers because it sports some built-in compilers out of the box like popular GCC compiler for C/C++ development. But some of the development tools we have to download via internet like one is if we have to do basic graphics development under Ubuntu then we should install libgraph libraries under Ubuntu which contains **graphics.h** header file and other important files for development. Basically, libgraph is not the part of the GNU project that’s why it doesn’t come preinstalled with Linux distributions.

***But What is Libgraph??***

> Libgraph is the implementation of the TurboC graphics API on GNU/Linux using SDL. You can get more info [here](https://savannah.nongnu.org/projects/libgraph/).

You might think that one can easily install libgraph just downloading the files from [here](http://download.savannah.gnu.org/releases/libgraph/). And configuring and installing on Ubuntu machine. But it isn’t simple, Wait. If you read carefully What is a libgraph section in the post you will notice, there is pre-requisite to install libgraph. And that is *SDL packages*. As libgraph is fully dependent upon SDL, we have to first install them. SDL stands for **Simple DirectMedia Layer**. Which is the platform on which our graphics program runs? And FYI Ubuntu doesn’t provide this out of the box. So follow the following simple steps to install required SDL version.

**Steps to install SDL.**

1\. Open terminal. (ctrl + shift + T).

2\. And copy pastes the following command and hit enter. It will download and update the packages in your system. (it requires internet connection).

\[code language=’bash’\] sudo apt-get update \[/code\]

![](https://mccshreyas.files.wordpress.com/2017/04/screenshot-82.png?resize=700%2C418)

3\. After that execute the following command to install SDL packages. (copy paste following command in terminal)

\[code language=’bash’\] sudo apt-get install libsdl-image1.2 libsdl-image1.2-dev guile-1.8 guile-1.8-dev \[/code\]

This command will install required SDL packages from internet.

**Steps to Install libgraph in Ubuntu.**   
1\. After that just download this libgraph installation files from the following link.

[Download Libgraph files. ](http://download.savannah.gnu.org/releases/libgraph/libgraph-1.0.2.tar.gz)

2\. Then copy the package to the home directory. And extract it there.

![](https://mccshreyas.files.wordpress.com/2017/04/screenshot-83.png?resize=700%2C394)

3\. Once it extracted open the folder. And right click on empty space and click on ‘Open in terminal’.

![](https://mccshreyas.files.wordpress.com/2017/04/screenshot-85.png?resize=700%2C394)

4\. In terminal execute following command one by one.

\[code language=’bash’\] . /configure  
sudo make install  
sudo cp /usr/local/lib/libgraph.\* /usr/lib \[/code\]

![](https://mccshreyas.files.wordpress.com/2017/04/screenshot-86.png?resize=700%2C394)

5\. And done. You have successfully installed libgraph. To check its installation type **man libgraph** and it will show up a manual page of libgraph.  
And one more thing. You can compile a graphics program by typing following I will terminal.

**For C++ program**

\[code language=’bash’\] g++ .cpp – lgraph \[/code\]

**For C program**

\[code language=’bash’\] gcc .c – lgraph \[/code\]

And also don’t forget to replace &lt;program\_name&gt; to your actual program name.

If you encountered any problem while doing this, then make sure that you hit comment below about that.

[Via](https://chahalgurpinder95.wordpress.com/2013/10/12/install-graphics-h-in-ubuntu/)