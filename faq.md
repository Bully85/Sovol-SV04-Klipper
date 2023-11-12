# FAQ Sovol-SV04- Klipper

## Z-Offset is not working. I get an error.

You have the wrong machine settings in your printer.cfg.
The SV04 is shipped with differnet boards. The STM32 or the GD32.
If you get an error when initiating a Z-Offset, choose the other chip variant in printer.cfg

## COPY, DUAL or MIRROR Mode won't working correctly.

Check the Start Codes in your Slicer.
Each GCode must be written in a single Line.

Please note, that only Cura <= 5.2 is working correctly at the moment!

## I get an "INVALID MESSAGE" in Mainsail

To fix the invalid message in Mainsail, SSH into Klipper and execute the following command:

```sh 
sudo nano ~/printer_data/systemd/moonraker.env
```
![moonraker.env1](docs/img/moonraker.env1.JPG)

Append "-g"  to the end of the "MOONRAKER_ARGS" Line: 
![moonraker.env2](docs/img/moonraker.env2.JPG)

Quit and save, then reboot. 

In Mainsail, click on 'invalid' and perform a soft repair. Your setup should now be ready!

## I have Problems with the Extruder Change and using Cura >= 5.3

Cura >=5.3 is currently not supported, but we are working on it.
