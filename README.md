dymoprint
=========

Linux Software to print with LabelManager PnP from Dymo


cloned for development from https://sbronner.com/dymoprint.html
then forked from https://github.com/computerlyrik/dymoprint

Changes:

- *some..*


### For ubuntu based distributions:
(should also work for debian, but not tested yet)
use **udev** and **modeswitch** configurations to work with the LabelManager PNP.
**modeswitch** changes the mode (and USB Id) from mass storage device to printer device.

    sudo cp 91-dymo-labelmanager-pnp.rules /etc/udev/rules.d/
    sudo cp dymo-labelmanager-pnp.conf /etc/usb_modeswitch.d/

and restart services with:

    sudo service udev reload

([more info](http://www.draisberghof.de/usb_modeswitch/bb/viewtopic.php?t=947))


### Font management

Fonts are managed via **dymoprint.ini**

You may choose any TTF Font you like

You may edit the file to point to your favorite font.

For my Arch-Linux System, fonts are located at e.g.

	/usr/share/fonts/TTF/DejaVuSerif.ttf

It is also possible to Download a font from
http://font.ubuntu.com/ and use it.

### Additional libraries used:
*(todo..)*
- PIL/PILLOW
- [pyqrcode](https://github.com/mnooner256/pyqrcode) (used v1.0)
- [pyBarcode](https://bitbucket.org/whitie/python-barcode) (used v0.7)

### ToDo
- (?)support multiple ProductIDs (1001, 1002) -> use usb-modeswitch?
- put everything in classes that would need to be used by a GUI
- allow font size specification with command line option (points, pixels?)
- print graphics
- vertical print
- add option to wait until free (e.g. not used by Cups)
