---
layout: post
title:  "First foray into Google Pigweed."
date:   2020-03-21 13:58:03 -0800
categories: io update
---
I have a small aeroponic garden at my home and by its nature is highly automated system.  It sustains extremely fast-growing fruits and herbs (Aeroponic plants grow 2-3 times faster than growing in soil).

I had been using an ESP8266 + Arduino mega combo board along with some open-source hydroponic control software.  It was great for a while, but soon discovered it was inadequate for the amount of automation and precision I need for this to work and be worthwhile.

I brainstormed for a better solution and decided to go with a dual-core Tensilica μC and went to work on coding a system from scratch (but using any available libraries to replace the faltering system ASAP).

Having already replaced main control of the garden with a ESP-32S microcontroller, I ordered a couple more and began the process of coding the entire system -- sensors and all -- for the newer device.  

This is about the time I discovered Google had just released [this library of modules](https://opensource.googleblog.com/2020/03/pigweed-collection-of-embedded-libraries.html) that could drastically improve my embedded code efficiency, so here we are!

At first glance, the Pigweed repository only has support for the STM32F429i discovery board, but if once you dig into Google's code review site you can see that there are [developers actively adding code for the esp-idf platform,](https://pigweed-review.googlesource.com/c/pigweed/pigweed/+/1240) which is my build target.

Just getting the first part of the code to work was a bit of a chore.   The worst part was having wait for the code to compile, then transfer then transfer to the test device while wait with my multimeter to check the pins.  The already-active CI of Pigweed makes it very appealing and hopefully it won't be too difficult to get working on these units as it would be a huge time saver.  

I already enabled github CI runners on my home linux machine and will document my progress (or lack-thereof) as I try to streamline my embedded development for this project.

As of today I accomplished the following:
 - [X] Set up github runners that automatically fetch code changes that I push and download them to my linux machine
 - [X] Started pigweed using the bootstrap, but with gcc-9 and python-3.8 (They only say that those versions work and didn't mention using or trying to use newer versions.  If I can't get some firmware compiled or flashed correctly I'll look here first to see if it might be the cause)
