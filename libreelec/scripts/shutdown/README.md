# LibreELEC Power Button
The code and instructions are taken from https://howchoo.com/g/mwnlytk3zmm/how-to-add-a-power-button-to-your-raspberry-pi and adapted for the usage with LibreELEC. It allows to safely turn on/shutdown a Raspberry Pi running LibreELEC via a hardware button, instead of (un-)plugging the power source or shutting it off via the GUI.

## Installing RPi.GPIO on LibreELEC
Either you can install RPi.GPIO via the program Add-Ons.
In case this does not work (maybe on older versions), you can install it directly:
```console
$ wget https://pypi.python.org/packages/source/R/RPi.GPIO/RPi.GPIO-0.6.2.tar.gz
$ tar zxf RPi.GPIO-0.6.2.tar.gz
$ cd RPi.GPIO-0.6.2
$ python setup.py install
```
This should create a directory *virtual.rpi-tools* in */storage/.kodi/addons/*

## Installing the shutdown scripts
- Move the python and the shell shutdown scripts to */storage/scripts/* (create the *scripts* directory, if necessary).
- Add the following lines to the `autostart.sh` script in */storage/.config/*. 
    ```bash
    (
      /storage/scripts/listen-for-shutdown.sh start
    ) &
    ```
## Installing the hardware button
Connect the two GPIO connectors of the power button to GPIO3 and GND (i.e. pins 5 and 6). For more details, follow the instructions at https://howchoo.com/g/mwnlytk3zmm/how-to-add-a-power-button-to-your-raspberry-pi to connect the button to the correct GPIO pins.
