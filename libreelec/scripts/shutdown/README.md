# LibreELEC Power Button
The code and instructions are taken from https://howchoo.com/g/mwnlytk3zmm/how-to-add-a-power-button-to-your-raspberry-pi and adapted for LibreELEC.

## Installing RPi.GPIO on LibreELEC
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
