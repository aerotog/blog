---
title: Just Embedded Things
date: "2020-10-12T22:26:05Z"
description: "Arduinos, and wires, and Pis, oh my!"
---

I recently started listening to the podcast [Embedded.fm](https://embedded.fm/). It's hosted by Elecia and Christopher White where they discuss a wide range of software engineering topics with different guests. Usually these topics are focused more on the embedded side of things, hence the name.

Around the same time, my 3D printer broken due to a shorted power connector for the heat bed. I found a solution online and ended up ordering a replacement terminal on [Digi-Key](https://www.digikey.com/). While I was searching for the right parts, I noticed how easy it was to find things on both Digi-Key and Amazon that many years ago I would have gone to Radio Shack with a 50/50 shot of actually finding.

Intrigued, I dug through my closet and found my old Arduino. Several years back, I had purchased it along with a strip of addressable LEDs for a costume project that didn't pan out. But having recently listened to interviews with different [makers](https://en.wikipedia.org/wiki/Maker_culture) from Embedded.fm, I was inspired to brush off the webs and hook it up.

While admiring the brightly flashing LEDs along with how easy they were control thanks to the [FastLED](http://fastled.io/) library. I started looking online to see what was new in the world of the embedded system hobby. What I found was quite surprising, to say the least.

Since I last looked at hobby embedded projects several years back, there seems to be a drastic increase in variety and availability of hardware along with a substantial drop in prices. (Thanks to the wild west of Chinese clones) On Amazon I found some WiFi enabled boards using the ESP8266 chip for less than $5 each which sounded like a steal.

A few short days later, I had a web server running on a microcontroller that could control LEDs. This was a Eureka moment for me. I had given up developing on the Arduino in part because it was so difficult to control/interface with. But with WiFi and the ability of the board to act as either a web server or a web client, the possibilities have grown drastically.

I spent the next several days scouring the internet for parts and ended up ordering large number of components from Amazon and AliExpress. My current plants include:
- WiFi enabled binary wall clock and weather indicator
- WiFi controlled Christmas tree lights
- WiFi controlled car ground effect and interior floor lighting
- Custom TV ambient light system using Raspberry Pi 3

The first three will all run off an ESP8266 chip while the last will use a Raspberry Pi 3 since I already had some of the required hardware lying around.

And of course in the age of cloud computing and single page apps, this wouldn't be complete without one: Autodesk offers a free online Arduino simulator called [Tinkercad](https://www.tinkercad.com/). This web app lets you design and test circuits as well as Arduino code in either block or text form. I found this immensely useful for testing various code ideas since flashing the development boards takes much longer. (Which also helps prolong the microcontroller's life since the EEPROM/flash memory writes are limited)

I've started a [new Github repo](https://github.com/aerotog/embedded) where I'll store my various Arduino sketches. I hope to have some if not all of these projects completed by year end. At the very least, this will be a good way to brush up on my C/C++. Depending on how they turn out, I'll probably make a separate blog post for each project with pictures.

~EOF~