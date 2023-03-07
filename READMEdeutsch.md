# Sovol-SV04-Klipper
All Config for the SV04 to work with Klipper Mirror and Copy (include images and description)

![KlipperSV04](docs/img/sv04klipper.png)


# Einleitung:
Diese Anleitung beschreibt, wie ihr euren SV04 Klippern könnt inkl COPY und MIRROR. Dafür wird ein spezielles Repo von Klipper benötigt.
## Benötigt:
- Raspberry Pi mit W-Lan
- Optional aber empfohlen original 7“ Touch
- Optional Kamera
- Putty oder ein anderes SSH Programm (https://putty.org/)
- FileZilla oder ein anderes SFTP Programm (https://filezilla-project.org/)
- Pi Imager (Programm https://www.raspberrypi.com/software/)
- Die von mir erstellten Config Dateien
- SD Karte max 8GB in Fat32 4096 formatiert

# Installation

Das Betriebssystem für den Raspberry findet ihr im Verzeichniss "[image Raspberry PI 3_4](https://drive.google.com/drive/folders/1rZepxzwUR5QTXRXcv5EBYin_gFiMcKVD)". dieses wird mit hilfe dem [Raspberry Pi Imager](https://www.raspberrypi.com/software/) auf eine SD-Karte gespielt. Achtet darauf gleich eure Wifi-Einstellungen anzupassen (diese findet ihr wenn ihr unten rechts auf das Zahnrad geht). Die firmware.bin im Verzeichnis "Firmware bin" kommt auf die SD Karte und wird mit ausgestecktem original Display (wird vorerst nicht mehr benötigt, da es nicht mehr funktioniert) auf den Drucker geflasht. Die Dateien aus dem "config" verzeichniss wird dann auf den Raspberry wie unten beschrieben oder direkt in der Mainsail Oberfläche (diese ist über die eingabe der IP adreasse des Raspberry welche im router ausgelesen werden kann erreichbar) übertragen. 

# Installation in bestehendes System: 

## Ohne Kiauh: 

beschreibung folgt .....

## Solltet ihr Kiauh nutzen:

- Logt euch per ssh auf den Raspberry und gebt folgenden befehl ein:
```sh
sudo nano kiauh/klipper_repos.txt.example
```

- dort fügt ihr am Ende folgende Zeile ein sieh Bild:
```sh
https://github.com/Bully85/klipper
```

![KiauhSV04](docs/img/klipper_repos.txt.PNG)

- Anschließend speichern mit [ strg X ]. 
- dann [ y ]
- Jetzt .example im Dateinamen löschen und Enter
- dann [ y ]
- Jetzt öffnen wir Kiauh mit dem Befehl
```sh
./kiauh/kiauh.sh
```
- Hier wählen wir [6] Settings
- Dann [1] Set custom Klipper repository
- [4] Bully85/klipper
- Und alles mit [ y ] bestätigen.

Fertig mit SSH

Nun müssen die Dateien und Ordner aus „config“ auf den Raspberry in das Verzeichnis eures Druckers kopieren Standard ist „printer_data“ sollte dies bei euch nicht der Fall sein, bitte in den config und .sh Dateien die pfade anpassen.
Am besten geht das mit einem SFTP Programm z.b [FileZilla](https://filezilla-project.org/) (Achtung PORT 22)