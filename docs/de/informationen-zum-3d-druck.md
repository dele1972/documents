# 3d Druck

## Allgemein

1. 3d Objekt besorgen (erstellen/organisieren)
2. (optional:) Drucker vorbereiten
3. Objekt sclicen → gcode erstellen
4. Objekt drucken

## 3d Objekt besorgen

### erstellen

- [FreeCAD](https://www.freecadweb.org/)
- [Fusion 360](https://www.autodesk.de/products/fusion-360/overview)
- [Tinkercad](https://www.tinkercad.com/)
- [SketchUp](https://www.sketchup.com/de)
- [AutoCAD](https://www.autodesk.de/products/autocad/overview?)
- [Sculptris](https://sculptris.de.uptodown.com/windows) (für Figuren, nur unter Windows)

### organisieren

- [MakerBot Thingiverse](https://www.thingiverse.com/)
- [MyMiniFactory](https://www.myminifactory.com/de/)

## (optional:) Drucker vorbereiten

- Kalibrierung
  - [Einstellfahrplan](https://www.3d-druck-community.de/showthread.php?tid=25055)
    - TODO: auswerten
  - (unvollständig) Extruder
    - [https://www.3d-druck-community.de/showthread.php?tid=29666](FLSUN Extruder kalibrieren)
      - TODO: auswerten
    - Pronterface (printrun)
      - install: `sudo apt-get install printrun`
      - [Printrun](https://www.pronterface.com/)
      - [Glossar: Pronterface](https://drucktipps3d.de/glossar/pronterface/)
    - https://sourcedigit.com/22048-how-to-list-connected-usb-devices-in-linux-ubuntu/
      - `lsusb` (QinHeng Electronics HL-340 USB-Serial adapter)
    - https://askubuntu.com/questions/254835/how-can-i-know-the-usb-port
      - `/dev/ttyUSB0`
    - im Programm
      - heat 185 (PLA)
      - Extrudieren
        - length 100mm
        - speed 100
      - Befehlszeile M106
      - Heat → ein
      - Extrudieren
      - nachmessen
      - Befehlszeile M503
        - !unbekannter Befehl!
          - [M503 unknown command](https://drucktipps3d.de/forum/topic/m503-unknown-command/)
          - TODO: auswerten
        - echo M92.........E99.60
        - (gewollt, z.B. 100) / (gemessen, z.B. 102) = 0.98
        - Das Ergebnis (0.98) * E-Wert aus Echo (99.60) = 97.65
        - eM92....E97.65
        - M500 speichern
        - M107 (?)
- calibrate stepper motors of all three arms
  - https://youtu.be/VXBr3MTs50c?t=2142    
- Temperature Tower etc.

## Objekt sclicen → gcode erstellen

- Slicer:
  - [Cura](https://ultimaker.com/de/software/ultimaker-cura)
- Es wird eine [STL](https://de.wikipedia.org/wiki/STL-Schnittstelle) Datei (aus dem CAD Programm oder Thingiverse) oder Projektdatei geladen.
- das zu verwendende Filament muss berücksichtigt werden!
  - Temperature Tower, etc.

### Filament

- PLA
  - wird ab 60°C weich (also auch nur bedingt Geschirrspülmaschinenfest)
  - Verarbeitung bei ca. 180-240°C
  - geringer Wärmeverzug
- PETG
  - kann nicht bemalt oder geklebt werden (nur mit Mehraufwand)
- ABB

## Objekt drucken

## Links

### Fachwörter

- Bowden
  - https://drucktipps3d.de/glossar/bowden/
- Extruder 
  - https://www.china-gadgets.de/ratgeber/3d-drucker-extruder-arten/

### Retraction Test

https://www.thingiverse.com/thing:2563909

### Infill mit Lücken

https://drucktipps3d.de/forum/topic/infill-mit-luecken/

### FLSUN Community 

- https://flsun.community/
- https://docs.google.com/document/d/1b_2N7NpQN2e96VPfVc_poLPOWwkM93tdAHZWOD4WEw8/edit?fbclid=IwAR3nnc5DWwfYtXiAY5R9YYlkbMFfzQt2wnyHScvodfq3ggfmakrHf2NsDsI
- https://www.facebook.com/groups/120961628750040/?ref=direct

### Delta Arm Fixture

- https://www.thingiverse.com/thing:4444539
- https://de.aliexpress.com/item/32880558099.html?spm=a2g0s.9042311.0.0.27424c4diEs71P
- https://de.aliexpress.com/item/32869473534.html?spm=a2g0s.9042311.0.0.27424c4d1ioYvo

