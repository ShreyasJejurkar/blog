---
id: 344
title: 'How to manually install Android/Windows Phone driver on Windows 7/8/8.1/10 PC'
date: '2016-12-22T10:13:30+00:00'
author: ShreyasJejurkar
layout: post
guid: 'https://mccshreyas.wordpress.com/?p=344'
permalink: /2016/12/22/how-to-manually-install-androidwindows-phone-driver-on-windows-788-110-pc/
publicize_twitter_user:
    - MCCshreyas
categories:
    - Windows
    - 'Windows phone'
---

Most of the users face the problem of smartphone connectivity to the PC due to lack of its driver. Most of the users face following problem while connecting their phone to the PC.

> 1\. I connected the phone to the PC via USB but can’t see in File explorer.  
> 2\. I connected phone but receive message like ‘malfunctioning USB device’.  
> 3\. Recive message like ‘Windows can’t find driver for the device’.

Generally, Windows OS will automatically install the driver for your phone as soon as you connect it to the PC. But sometimes it didn’t happen (most of the time because of antivirus. Antivirus blocks the installation of the driver) and at that moment we have to install the driver manually.

Many of us will try to download drivers for the phone from the internet. But Windows already have it and **you don’t need to download drivers for it from the internet**. By default, Windows consider your phone as **‘Portable device’** and for portable devices, it automatically installs **MTP USB** driver when you first connect your phone to the PC. But if you want to install this driver manually you can follow the following steps. And also those who are facing above problems can follow the steps to manually install phone driver. In my case, the phone is Lumia 520 (Windows Phone) but these **steps are also applicable for Android devices too**.

**Steps**  
1\. First, connect your phone to the PC via a working USB cable to the working USB port.  
2\. After that on PC press **Windows logo key + X** simultaneously. From the menu open **Device manager**.

![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-20161221204457.png?w=700)

3\. In device manager, you will see your mobile name under **Other devices** section and will be having exclamation mark under it.

![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-20161221211334.png?w=700)

4\. Right-click on your mobile name and click on the first option i.e. **update driver software**.

![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-20161221211552.png?w=700)

5\. You will see a new window asking you **How do you want to search for driver software?** in that **select second option** i.e. ‘Browse my computer for driver software’ and click on it.

![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-20161221211753.png?w=700)

6\. On the second window click on the option named as **Let me pick from a list of device drivers on my computer**.  
7\. Another new window will open and will show you common hardware types. From that list look for **portable devices** and click on it.

![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-2016122215371.png?w=700)

8\. In next window select **MTP USB device** (select one among them) and click on next button. And wait for seconds so that Windows will install the driver for your phone.

![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-20161222153811.png?w=700)

9\. If installation gets successfully you will receive the message like **Windows has successfully updated the driver software for your device**.  
10\. And <u>if not then select another MTP USB driver and try with that</u>.

![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-20161222153928.png?w=700)

11\. After installation successful, you can access your files of your phone from ‘My PC’ (file explorer). You can see your phone under Devices &amp; drivers.

![](http://mccshreyas.files.wordpress.com/2016/12/savedpicture-20161222154030.png?w=700)

So this is the simplest method by which you can install the driver of your smartphone (Android or Windows Phone) on PC.  
These steps are applicable to Windows 7/8/8.1/10