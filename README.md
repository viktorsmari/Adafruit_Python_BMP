Adafruit Python BMP
===================

Python library for accessing the BMP series pressure and temperature sensors like the BMP085/BMP180 on a Raspberry Pi or Beaglebone Black.

Designed specifically to work with the Adafruit BMP085/BMP180 pressure sensors ----> https://www.adafruit.com/products/1603

To install, download the library by clicking the download zip link to the right and unzip the archive somewhere on your Raspberry Pi or Beaglebone Black.  Then execute the following command in the directory of the library:

````
sudo python setup.py install
````

Make sure you have internet access on the device so it can download the required dependencies.

See examples of usage in the examples folder.

#### Install munin plugins

To use the munin plugins do the following:

Copy the files from the munin folder to */usr/share/munin/plugins* (Ubuntu 14.04)

Create symlinks:

`sudo ln -s /usr/share/munin/plugins/i2c_pressure /etc/munin/plugins/`

`sudo ln -s /usr/share/munin/plugins/i2c_temperature /etc/munin/plugins/`

The munin-node needs root access for the IO pins, add the following at the bottom of this file: 

*etc/munin/plugin-conf.d/munin-node*

```
[i2c_pressure]
user root

[i2c_temperature]
user root
```

Restart munin-node

Adafruit invests time and resources providing this open source code, please support Adafruit and open-source hardware by purchasing products from Adafruit!

Written by Tony DiCola for Adafruit Industries.
MIT license, all text above must be included in any redistribution
