# FAQ Sovol-SV04- Klipper

## Z-Offset funktioniert nicht. Ich bekomme eine Fehlermeldung.

Du hast die falschen Maschinen-Einstellungen in deiner _printer.cfg_.

Der SV04 wird mit verschiedenen Chips ausgeliefert. Dem STM32 oder dem GD32.

Bekommst Du die Fehlermeldung, wähle die andere Chip-Variante in deiner printer.cfg

## COPY, DUAL oder MIRROR Mode funktionieren nicht korrekt

Prüfe den Startcode in deiner Slicer-Software
Jeder GCode Befehl muss in einer separaten Zeile stehen.

Bitte beachte, dass derzeit nur Cura <= 5.2 korrekt funktioniert.

## Ich bekomme "INVALID MESSAGE" im Mainsail

Um die _Invalid Message_ in Mainsail zu beheben, bitte mit SSH in der Klipper-Instanz anmelden und folgenden Befehl absetzen

```sh 
sudo nano ~/printer_data/systemd/moonraker.env
```
![moonraker.env1](docs/img/moonraker.env1.JPG)

Hänge "-g"  am Ende der "MOONRAKER_ARGS" Zeile an:
![moonraker.env2](docs/img/moonraker.env2.JPG)

Verlassen mit Speichern und dann Reboot.

Im Mainsail, klicke auf 'invalid' und führe einen Soft-Repair durch. Deine Installation sollte nun korrekt funktionieren.

## Ich habe Probleme beim wechseln des Extruders und benutze Cura >= 5.3

Cura >=5.3 ist derzeit nicht unterstützt. Wir arbeiten daran.