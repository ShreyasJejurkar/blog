---
id: 504
title: 'How to &#8211; Install R and R studio on Ubuntu'
date: '2018-03-29T07:14:50+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=504'
permalink: /2018/03/29/how-to-install-r-and-r-studio-on-ubuntu/
timeline_notification:
    - '1522307693'
publicize_twitter_user:
    - MCCshreyas
image: /wp-content/uploads/2018/03/rstudio.png
categories:
    - Ubuntu
---

R is the most popular programming language in the field of Big data analysis and data science. Python is also there on the other hand but R has a much bigger library for statistical packages. And also R builds in data analysis functionality by default, whereas Python relies on packages. So the most preferred language for data analysis is R.

So in my today’s blog post am going to demonstrate how you can download R and R studio which is an IDE meant for faster R development on Ubuntu. Below are the steps that you should follow in order to get R and R studio on your machine.

So let’s get started…

### Steps :

1\. Open the terminal on your machine.

2\. Add a key to APT for authentication of packages that we are going to download in some next steps. Enter below command and hit enter.

\[code language=’bash’\] sudo apt-key adv –keyserver keyserver.ubuntu.com –recv-keys E084DAB9 \[/code\]  
3\. Then add the repository URL to APT.

\[code language=’bash’\] sudo add-apt-repository ‘deb https://ftp.ussg.iu.edu/CRAN/bin/linux/ubuntu xenial/’ \[/code\]

4\. Then update the package list.

\[code language=’bash’\] sudo apt-get update \[/code\]

5\. Then install *r-base* package which is the default base package for R programming language.

\[code language=’bash’\] sudo apt-get install r-base \[/code\]

6\. Then r-base development package.

\[code language=’bash’\] sudo apt-get install r-base-dev \[/code\]

Now at this moment, you have install R on your machine. You can use R by typing R on the terminal and hitting enter. After you do that you will be prompted to R shell on which you can type one by one command and use it.

![R on ubuntu.png](https://mccshreyas.files.wordpress.com/2018/03/r-on-ubuntu.png?resize=700%2C399)

In case you want to use R studio which an exclusive IDE for R you have to follow below additional steps.

### Steps :

1\. Install gdebi core package.

\[code language=’bash’\] sudo apt-get install gdebi-core \[/code\]

2\. Then download the latest version of R studio

\[code language=’bash’\] wget https://download2.rstudio.org/rstudio-server-1.1.442-amd64.deb \[/code\]

3\. Then install JPEG runtime library

\[code language=’bash’\] sudo apt install libjpeg62 \[/code\]

4\. <span style="color:#ff0000;">NOTE – If your **Ubuntu version is between 16.10 to 17.04** then you have to install some additional packages on your machine. And if your Ubuntu version is above 17.04 then you can proceed to <span style="color:#0000ff;">step 8</span>. </span>

5\. Download the libgstreamer packages and install them.

\[code language=’bash’\] wget http://ftp.ca.debian.org/debian/pool/main/g/gstreamer0.10/libgstreamer0.10-0\_0.10.36-1.5\_amd64.deb  
wget http://ftp.ca.debian.org/debian/pool/main/g/gst-plugins-base0.10/libgstreamer-plugins-base0.10-0\_0.10.36-2\_amd64.deb \[/code\]

6\. Install those packages.

\[code language=’bash’\] sudo dpkg -i libgstreamer0.10-0\_0.10.36-1.5\_amd64.deb  
sudo dpkg -i libgstreamer-plugins-base0.10-0\_0.10.36-2\_amd64.deb \[/code\]

7\. Put those packages on hold so that they won’t get overwritten by the next software update.

\[code language=’bash’\] sudo apt-mark hold libgstreamer-plugins-base0.10-0  
sudo apt-mark hold libgstreamer0.10 \[/code\]

8\. Now its time to install R studio from the package we have downloaded in step 2.

\[code language=’bash’\] sudo gdebi rstudio-server-1.1.442-amd64.deb \[/code\]

And done. You have just installed R studio on your machine. You can access it by searching for ‘ R studio’ application on your machine. It will be there on your machine. If you face any problem while installing R or R studio make sure that you ask in the comment section below.

[via](https://medium.com/@GalarnykMichael/install-r-and-rstudio-on-ubuntu-12-04-14-04-16-04-b6b3107f7779)