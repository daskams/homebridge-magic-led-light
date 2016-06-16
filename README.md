

# Homebridge MagicBlue LED Light Bulb Plugin

This plug-in enables you to control your MagicBlue LED light bulb.

## Connecting and setting up

The light bulb uses Bluetooth low energy. This means that your Raspberry Pi needs to have Bluetooth in some way. You will need to know the mac address of the light bulb. You can discover it by installing bluez and everything to your Raspberry Pi. A possible guide can be found [here](http://www.elinux.org/RPi_Bluetooth_LE). However you don't need to compile it yourself. I find the version in the repositories to be sufficient. You can then discover the mac address by running the command shown below. The mac is "FB:00:E0:82:AA:1F" in this case.

```
	pi@raspberrypi:/var/homebridge/own_plugins/homebridge-magic-blue-bulb$ sudo hcitool lescan
	LE Scan ...
	FF:FF:C8:5D:68:9E Eve
	FF:FF:C8:5D:68:9E Eve Thermo
	33:03:44:44:AA:5C (unknown)
	33:03:44:44:AA:5C Eve Door
	FB:00:E0:82:AA:1F (unknown)
	22:20:7B:99:D3:AF (unknown)
	FB:00:E0:82:AA:1F LEDBLE-A582661F    <--- this is your light bulb
	22:20:7B:99:D3:AF (unknown)
```

## Installation

This project is currently not submitted to npmjs so you will need to manually download this plug-in put it somewhere on your Raspberry Pi, download the dependencies and alter the command you run for homebridge to find this plug-in. How this is done can be seen on this [page](https://github.com/nfarina/homebridge).

## Config.json file

```json
	{
	    "accessory" : "magic-blue-bulb",
	    "name" : "MagicBlue",
	    "mac" : "FB:00:E0:82:AA:1F"
	}
```

| Key           | Description                                                                        |
|---------------|------------------------------------------------------------------------------------|
| accessory     | Required. Has to be "ws2801-led-strip"                                             |
| name          | Required. The name of this accessory. This will appear in your homekit app         |
| mac           | Required. The mac address that you discovered earlier                              |

## Issues
I have not tested this plugin in any shape or form. It works great for me but I did not test any other systems or anything. Feel free to use it and make suggestions in case of bugs. I do not take responsibility for any issues or damages this code might cause for you. Use at your own risk.
