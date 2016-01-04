Notes for an eventual document on power management

Ideas sourced from here, where original contributors are mentioned:
http://babaawesam.com/2014/01/24/power-saving-tips-for-raspberry-pi/

##Underclocking the RPi2. 

tested

Adding these lines to your config.txt (assuming RPi2 has not been overclocked)
* arm_freq_min=250
* core_freq_min=100
* sdram_freq_min=150

Do not add bullets before the lines. Reboot after adding the lines.

With these lines added, the processor runs at 250 mhz when idle, and returns to 900 mhz when active. I have seen no performance decrease from this change.

You can check your processor speed with the command

`cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_cur_freq`

##Powering off USB & ethernet ports between loops (or permanently!)

tested

https://github.com/codazoda/hub-ctrl.c

worst case: returns to normal after a reboot

##Powering off HDMI

not yet tested

Warning, does not return to normal after a reboot. Recommend to add the HDMI power on command to crontab @reboot.

If your system is headless (no video output) you can turn off the HDMI port with:

`sudo /opt/vc/bin/tvservice -o`

to turn it back on:

`sudo /opt/vc/bin/tvservice -p`

This command will save you around 20-30mA.
