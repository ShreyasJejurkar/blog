---
id: 862
title: 'How to &#8211; Hide Prefetch request from Network Tab in Chrome DevTools'
date: 2022-09-17T06:20:46+00:00
author: ShreyasJejurkar
layout: post
guid: 'https://shreyasjejurkar.com/?p=862'
slug: how-to-hide-prefetch-request-from-network-tab-in-chrome-devtools
image: /wp-content/uploads/2022/09/pexels-photo-1482061.jpeg
categories:
    - Programming
tags:
    - chrome
    - developer
    - devtools
---

If you are a Web developer and working on a Full Stack application, you might have notice that the browser ( in my case Chrome) does send prefetch requests to your API endpoints before the actual API calls.

This is actually useful to improve performance but this can be very confusing when you are debugging applications from the front-end to the back-end and monitoring API calls in the network tab. Prefetch requests just clutter the network tab and we miss our actual XHR request to see what is happening.

So in this post, I will tell you the way through which you would be able to filter out prefetch requests from the network tab and can able to focus on actual XHR API calls.

**Steps**

1. Open Chrome developer tools by right-clicking on the page and clicking on inspecting or by pressing the shortcut CTRL + SHIFT + I.
2. Navigate to the Network tab (4th one most likely).
3. And in the filter textbox type `-method:OPTIONS`.We add a filter for HTTP OPTIONS method because prefetch calls use HTTP OPTIONS.

<figure class="wp-block-image size-full is-resized">![prefetch filter](https://i0.wp.com/shreyasjejurkar.com/wp-content/uploads/2022/09/image.png?resize=297%2C188&ssl=1)</figure>Once you perform the above steps, all prefetch API calls will be filtered out and you will only see XHR calls.