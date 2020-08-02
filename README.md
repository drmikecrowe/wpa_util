# rpi-auto-wifi

## Raspberry Pi Wifi Auto-Connect for Headless Systems

An extension of [wpa_util](https://github.com/jingsong-liu/wpa_util)

A very RPi specific connection algorythm:

-   First test if wpa_supplicant reconnected us
-   Next, check if we can force a reconnect
-   Next, try and connect to any open networks
-   Next, try and connect to any network where WPS is enabled
-   Wait 6s and repeat for 1m

Misc logging logged to syslog

## Installation

rpi-auto-wifi is distributed on [PyPI](https://pypi.org) as a universal wheel and is available on Linux/macOS and Windows and supports Python 2.7/3.5+ and PyPy.

```{.sourceCode .bash}
$ sudo pip3 install rpi-auto-wifi
```

Because this is expected to run as root, install via pip as root.

## License

rpi-auto-wifi is distributed under the terms of both

-   [MIT License](https://choosealicense.com/licenses/mit)

## Expected usage:

```
sudo python3 -m rpi_auto_wifi
if [ "$?" != "0" ]; then
    shutdown -r now
fi
```

## TESTING

NOTE: Testing is only half-baked at the moment
