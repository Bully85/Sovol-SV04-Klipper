# FAQ Sovol-SV04- Klipper

## Z-Offset is not working. I get an error.

You have the wrong machine settings in your printer.cfg.
The SV04 is shipped with differnet boards. The STM32 or the GD32.
If you get an error when initiating a Z-Offset, choose the other chip variant in printer.cfg

## COPY, DUAL or MIRROR Mode won#t working correctly.

Check the Start Codes in your Slicer.
Each GCode must be written in a single Line.

Please note, that only Cura <= 5.2 is working correctly at the moment!

