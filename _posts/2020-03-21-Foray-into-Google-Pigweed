---
layout: post
title:  "First foray into Google Pigweed."
date:   2020-03-21 13:58:03 -0800
categories: io update
---
I have a small aeroponic garden at my home and by its nature should be a highly automated system.  It sustains extremely fast-growing fruits and herbs (Aeroponic plants grow 2-3 times faster than growing in soil).

I had been using an ESP8266 + Arduino mega combo board and some hydroponic control software I found, but due to the limitations of that board I discovered it was inadequate for the amount of automation and precision I need for this to be worthwhile.

Having already replaced partial control of the garden with a dual ESP-32S microcontroller, I ordered a couple more and began the process of moving the entire system, sensors and all to the newer devices.  This is about the time I discovered Google had just released this library of modules that could drastically improve my embedded code efficiency, so here we are!

At first glance, the Pigweed repository only has support for the STM32F429i discovery board, but if once you dig into Google's code review site you can see that there are developers actively adding code for the esp-idf platform, which is what I'll be targeting with my builds.

Just getting the first part of the code working was a bit of a chore, with having to constantly wait for the code to compile, then transfer to the device to test changes.  The already-active CI of Pigweed makes it very appealing and hopefully it won't be too difficult to get working on these units as it would be a huge time saver.  

I already enabled github CI runners on my home linux machine and will document my progress (or lack-thereof) as I try to streamline my embedded development for this project.
