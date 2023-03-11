# Sovol-SV04-Klipper
All Config for the SV04 to work with Klipper Mirror and Copy (include images and description)

![KlipperSV04](docs/img/sv04klipper.png)

# Spenden/donate


[![Donate with PayPal](https://raw.githubusercontent.com/stefan-niedermann/paypal-donate-button/master/paypal-donate-button.png)](https://www.paypal.com/donate/?hosted_button_id=L85ULXXQKALP6)

# _Für die deutsche Anleitung wählt bitte READMEdeutsch.md_

# Introduction:

First check your Chip if you have STM or GD. you can open your electikbox and look for it or you can test the Z-Tilt in Mainsail (If there is an error you have the GD Chip see printer.cfg)

This guide describes how you can klipper your SV04 including COPY and MIRROR. A special repo from
Klipper is required for this.

#  In progress:
Currently Cura 5.3 is not supported! but we are working on it...

# What's up?!!!

- Copy Mode (with different temperatures)
- Mirror Mode (with different temperatures)
- Dual mode
- Single mode
- Bed mesh area
- Input shapers
- and much more

## What you needed:

- Raspberry Pi with WiFi
- Optional but recommended original 7" touch
- Optional camera
- Putty or another SSH program (https://putty.org/)
- FileZilla or another SFTP program (https://filezilla-project.org/)
- Pi Imager (Program https://www.raspberrypi.com/software/)
- The config files I created
- SD card max 8GB formatted in Fat32 4096

# Installation

The operating system for the Raspberry can be found in the "[image Raspberry PI 3_4](https://drive.google.com/drive/folders/1rZepxzwUR5QTXRXcv5EBYin_gFiMcKVD)" directory. this is played onto an SD card using the [Raspberry Pi Imager](https://www.raspberrypi.com/software/). Be sure to adjust your wifi settings right away (you can find them by clicking on the cog wheel in the bottom right corner). The firmware.bin in the "Firmware bin" directory is placed on the SD card and flashed onto the printer with the original display unplugged (it is no longer needed for the time being because it no longer works). The files from the "config" directory are then transferred to the Raspberry as described below or directly in the Mainsail interface (this can be accessed by entering the IP address of the Raspberry, which can be read in the router).



# Installation in existing system:

## Without Kiauh:

comming soon

## If you use Kiauh:
- Log in to the Raspberry via ssh and enter the following command:
```sh
sudo nano kiauh/klipper_repos.txt.example
```

- there you add the following line at the end (see picture):
```sh
https://github.com/Bully85/klipper
```

![KiauhSV04](docs/img/klipper_repos.txt.PNG)

- Then save with [ Ctrl X ].
- then [ y ]
- Now delete .example in the file name and Enter
- then [ y ]
- Now we open Kiauh with the command
```sh
./kiauh/kiauh.sh
```
- Here we choose [6] settings
- Then [1] set custom clipper repository
- [4] Bully85/klipper
- And confirm everything with [y].

Done with SSH

Now the files and folders must be copied from "config" to the directory of your printer on the Raspberry. The default is "printer_data". If this is not the case for you, please adjust the paths in the config and .sh files.
The best way to do this is with an SFTP program, e.g. [FileZilla](https://filezilla-project.org/) (attention PORT 22)
