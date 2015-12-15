# Compact-APS

This repository contains a compact hardware configuration for a DIY APS system based on the OpenAPS toolset. The goal of this build is to put everything needed for an OpenAPS-based implementation in a single box, except for the pump and CGM sensor of course! Pictures are available in the Images folder of this repository. The custom case files are in the Case folder.

(Note, in the pictures the thing is held together by elastics, but this is only because I have not yet received the bolts I ordered. :)

Dimensions:
- 10 cm long
- 6.2 cm wide
- 3 cm high

The device supports reading from Medtronic pumps & CGM, as well as Dexcom (I think! I don't have a Dexcom to test with...). It includes Wifi and BLE hardware support as well, via USB dongles. v2 will include a small OLED display for key information.

The main tactic for reducing the footprint was to reverse one of the USB ports on the RPi2, so that the Carelink USB dongle is positioned over the RPi and not protrude outwards.

Due to the inclusion of an Adafruit PowerBoost charger, the device charges like a mobile phone - no need to shut it down and swap around USB cables. Just plug it in and it will charge while running. An attempt was made to include wireless charging as well - this was not immediately successful so will be added in a later version if possible.

Device runs for me for over 5 hours on a charge, with 3 SSH sessions active, 1 bluetooth command sent each minute, and one pump request (iter_glucose_hours 3) sent every minute.

The "Moon and stars" face on the top cover helps to remember how to place the device to have the optimum angle for communicating with the Carelink USB. If the face is looking at you, then it is likely in a good position for communication. :)

v1 design includes the following components:

- 1 Raspberry Pi 2 + SD card with NOOB Raspian and some extra space (standard stuff)
- 1 standard dual-port PCB-mountable USB connector (dismantled and rebuilt to face backwards - this would take some time to explain and so I will describe it further at a later time)
- 1 Carelink USB dongle
- 1 Adafruit PowerBoost 1000C
- 1 Power switch for the PowerBoost 1000C
- 1 Duracell DRSI9220 Lithium Ion battery (Samsung Galaxy Note replacement battery) - 2500 mAh
- 1 mobile phone battery connector (salvaged from an inexpensive Samsung mobile phone)
- 1 Wixel (to collect data from Dexcom CGM in an Xdrip configuration. Not tested as I don't have a Dexcom...)
- 1 Asus USB-BT400 Bluetooth 4.0 dongle (for Xdrip configuration but also might be used to connect via an app one day)
- 1 Edimax EW-7811UN Nano WiFi adapter
- 1 Medtronic remote control MMT-503EU, plus A23 12-volt battery, plus 3 x 4N25 optocouplers (this was for an experiment. it worked, but it was irritating, so it will be removed in v2)
- 1 home-designed and printed 3D case (files available in this repo)
- m2.5 x 8 nuts & bolts (cut down to various lengths as needed)
- m2.5 x 30 nuts & bolts (cut down to various lengths as needed)

+ bits of wire, solder, heat-shrink, the occasional piece of electrical tape, tools, sweat, tears.

v2 design will have the following changes:

- The Medtronic remote will likely be removed
- An Adafruit OLED display will be added in its place
- Momentarily switches (spring-loaded slider to prevent accidental activation) may be added for "yes/no" user responses to prompts on the OLED display - if needed
- Wireless charging (if it works) 
- A switch for "exercise mode" - a mode I intend to add which warns the APS I am exercising and reduces the aggressivity of the correction algorithm

A description of the build will be developed over time and posted to this repo. As a start, step 1 in the process was to strip down the RPi - desolder the GPIO pins and remove the outermost dual-USB port. This was not straightforward and I destroyed the first Pi I tried it on. Then I came across this tutorial and it became easy:

https://blog.adafruit.com/2014/11/03/diet-raspberry-pi-its-only-wafer-thin-raspberry_pi-raspberrypi/

More information to come when I have further time.

Best wishes, Andrew Warrington
