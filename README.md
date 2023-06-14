# Sovol-SV04-Klipper
This repository contains all the necessary configuration files for the SV04 to work with Klipper's Mirror and Copy modes, including images and descriptions.

![KlipperSV04](docs/img/sv04klipper.png)

# Spenden/Donations

[![Donate with PayPal](https://raw.githubusercontent.com/stefan-niedermann/paypal-donate-button/master/paypal-donate-button.png)](https://www.paypal.com/donate/?hosted_button_id=L85ULXXQKALP6)

# _Für die deutsche Anleitung wählt bitte READMEdeutsch.md_

# Introduction:

Before starting, verify whether your chip is STM or GD. You can do this by opening your electric box and checking, or by testing the Z-Tilt in Mainsail. If an error occurs, it means you have the GD Chip (see printer.cfg for details).

This guide will help you set up your SV04 with Klipper, including the COPY and MIRROR modes. A special Klipper repository is required for this.


# In Progress:

Cura 5.3 is currently not supported, but we are actively working on it.


# Features

- Copy Mode (supports different temperatures but does not support first layer settings for the right Extruder)
- Mirror Mode (supports different temperatures but does not support first layer settings for the right Extruder)
- Dual mode
- Single mode
- Bed mesh area
- Input shapers
- Display functionality
- And much more


# Requirements

- Raspberry Pi with WiFi
- Optional but recommended: Original 7" touch screen
- Optional: Camera
- Putty or another SSH program (https://putty.org/)
- FileZilla or another SFTP program (https://filezilla-project.org/)
- Pi Imager (https://www.raspberrypi.com/software/)
- The configuration files provided in this repository
- SD card (max 8GB, formatted in Fat32 4096)


# Installation

The operating system for the Raspberry Pi can be found in the "[image Raspberry PI 3_4](https://drive.google.com/drive/folders/1rZepxzwUR5QTXRXcv5EBYin_gFiMcKVD)" directory. This should be installed onto an SD card using the [Raspberry Pi Imager](https://www.raspberrypi.com/software/). Make sure to adjust your WiFi settings immediately (you can find them by clicking on the cog wheel in the bottom right corner). The firmware.bin file in the "Firmware bin" directory should be placed on the SD card and flashed onto the printer with the original display unplugged (the original display is not needed at this stage as it will not function). The files from the "config" directory should then be transferred to the Raspberry Pi as described below or directly in the Mainsail interface (this can be accessed by entering the IP address of the Raspberry Pi, which can be found in your router).


# Installation in Existing System

## Without Kiauh

Coming soon.

## If you use Kiauh
- Log in to the Raspberry Pi via SSH and enter the following command:

```sh 
sudo nano kiauh/klipper_repos.txt.example
```

- Add the following line at the end (see image below):

```sh 
https://github.com/Bully85/klipper
```

![KiauhSV04](docs/img/klipper_repos.txt.PNG)

- Save the file with Ctrl+X, then press Y. 
- Remove ".example" from the file name and press Enter, then Y. 
- Open Kiauh with the command 
```sh 
./kiauh/kiauh.sh
```
- Choose [6] 
- Then [1] to set the custom Klipper repository
- Select [4] "Bully85/klipper"
- Then confirm everything with [y].

Exit SSH by pressind Ctrl+D.

Now, the files and folders from the "config" directory must be copied to your printer's directory on the Raspberry Pi. The default is "printer_data". If this is not the case for you, please adjust the paths in the config and .sh files. 
The best way to do this is with an SFTP program, such as [FileZilla](https://filezilla-project.org/) (note: use PORT 22).


# Fixing the Invalid Message in Mainsail

To fix the invalid message in Mainsail, SSH into Klipper and execute the following command:

```sh 
sudo nano ~/printer_data/systemd/moonraker.env
```
![moonraker.env1](docs/img/moonraker.env1.JPG)

Append "-g"  to the end of the "MOONRAKER_ARGS" Line: 
![moonraker.env2](docs/img/moonraker.env2.JPG)

Quit and save, then reboot. 

In Mainsail, click on 'invalid' and perform a soft repair. Your setup should now be ready!
