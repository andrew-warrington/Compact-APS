# Compact-APS

This repository contains a compact hardware configuration for a DIY APS system based on the OpenAPS toolset. The goal of this build is to put everything needed for an OpenAPS-based implementation in a single box, including the battery. Pictures are available in the Images folder of this repository. The custom case files are in the Case folder.

V1 is designed for a Raspberry Pi / Carelink config
V3.2 is designed for a Edison / TI USB CC1111 dongle config (mmeowlink)

If you are just starting out, I recommend the Edison v3.2 due to smaller size and longer battery life.

## V1 (Raspberry Pi) info

- Battery life 5 hours, with 5 hours recharge time while running.
- 10 cm long
- 6.2 cm wide
- 3 cm high

The device supports reading from Medtronic pumps & CGM, as well as Dexcom (I think! I don't have a Dexcom to test with...). It includes Wifi and BLE hardware support as well, via USB dongles.

The main tactic for reducing the footprint was to reverse one of the USB ports on the RPi2, so that the Carelink USB dongle is positioned over the RPi and not protrude outwards.

Due to the inclusion of an Adafruit PowerBoost charger, the device charges like a mobile phone - no need to shut it down and swap around USB cables. Just plug it in and it will charge while running. An attempt was made to include wireless charging as well - this was not immediately successful so will be added in a later version if possible.

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

Getting started? I started here, learning to desolder components on the Raspberry Pi.
https://blog.adafruit.com/2014/11/03/diet-raspberry-pi-its-only-wafer-thin-raspberry_pi-raspberrypi/

## V3.2 (Edison) info:
- Battery life 31+ hours, with 2.5 hours recharge time while running.
- 9.6 cm long
- 6.1 cm wide
- 2.8 cm high
... with rounded edges to be easier to put in a pocket!

v3.2 design includes the following components:
- 1 Intel Edison with mini-breakout board
    - includes WiFi and BLE on board
    - the Edison USB pins 4 & 5 are shorted to force it persistently into host mode
- 1 custom USB OTG adapter, made small to save space
- 1 power switch
- 2 Duracell DRSI9220 Lithium Ion battery (Samsung Galaxy Note replacement battery), in series for 7.4V
- 1 FatShark 7.4 LiIon battery, which was disassembled to yield:
    - The balance charging circuit
    - The balance charging cable
    - The power cable
- 1 FatShark 7.4v 1000mAh wall charger
- 1 TI USB dongle CC1111EMK868-915 running the excellent subg-rfspy and managed via mmeowlink
- 1 Medtronic remote controlled via Edison GPIO (which most people would not need)

The case was further simplified over v1 to not require any screws or bolts.... also because this helps reduce size! The top snaps on and off with clips.

I don't have time to document everything for this build at the moment unfortunately, but am happy to interact, answer individual questions, and improve the documentation from there based on what questions come up. Contact me if you want help.

Best wishes, Andrew Warrington
