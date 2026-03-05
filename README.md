# ESPHome-1.28-Inch-round-LCD-Remote
Using ESPHome to build a remote control with a generic 1.28 inch round lcd display containing an ESP32-C3, GC9A01A driver and cst816 touchscreen.

I purchased a couple round 240x240 LCD displays that have:
1. ESP32-C3 cpu
2.  GC9A01A graphics driver
3.  cst816 touchscreen driver

Front:
![Alt text](images/Product-Front-View.webp)   

Rear:

I've never been able to get the code working for them, until I tackled them this past week. I use Home Assistant and esphome for most of my devices now, so I stay on that platform. In looking at various esphome components, i found the older lgvl driver was working for some folks but i had issues.. I ended up staying with the mipi_spi component.  A lot of the code was home grown but I relied on Copilot and chatgpt some to help pull in some of the mundane details (with, of course, a lot of cleanup, as the LLM's available for free understand a lot of the ESPHome design, but often end up mixing in older Arduino code and breaking things...)

What i have in this version is a remote that has one way communication from the source system, screen controls and pages. It uses ESPNow as the communication component so Home Assistant is NOT needed, nor is a WiFi network. Since this application in particular is for a camper/rv I cannot rely on those items being present (i.e. when i'm on the road the home network isnt around!). When testing my camper I found its a bit more work than i want to turn on lights and fans from inside.. having to unlock the phone then launch the website, then log in, then change things.  This remote is simpler, direct access, and encrypted (perhaps weakly, but still sufficient) and instantly on.

Note that there are companion projects for this.. I will upload those repos shortly. They include the actual camper monitor IoT device and an in-car monitor.
