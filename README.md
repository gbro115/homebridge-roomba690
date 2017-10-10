homebridge-roomba690
=========

**This has not yet been uploaded to npm!**

This Homebridge plugin adds support for the Roomba 690.

Unfortunately, the [homebridge-roomba980](https://github.com/steedferns/homebridge-roomba980) plugin doesn't work with the Roomba 690. This is ultimately due to the 690 not supporting dorita980's getMission() method. homebridge-roomba690 works around this by making use of the methods the 690 does support.

It also adds a BatteryService, allowing you to check on the charging status of the 690.

## Features

* Start / stop Roomba *Hey Siri, turn on the Roomba*
* Check charging status *Hey Siri, is the Roomba charging?*
* Check battery status

## Installation

`npm install -g homebridge-roomba690`

## Homebridge configuration

Add to your config.json's accessory section:

```
{
    "bridge": {
	"name": "Homebridge",
	"username": "CD:22:3D:E3:CE:30",
	"port": 51826,
	"pin": "123-45-678"
    },

    "description": "My Homebridge",

    "platforms": [],

    "accessories": [
	{
	    "accessory": "Roomba690",
	    "model":"690",            
	    "name": "Roomba",
	    "hostname": "ip-address-of-your-roomba",            
	    "blid":"blid-of-your-roomba",
	    "password":"password-for-your-roomba"
	}
    ]
}
```
To obtain your BLID and Password for your Roomba, refer to [dorita980](https://github.com/koalazak/dorita980#how-to-get-your-usernameblid-and-password)

The Model and Name options can be set to whatever you'd like.

## Credits

This code was built upon the work in the following projects:

* [homebridge](https://github.com/nfarina/homebridge)
* [dorita980](https://github.com/koalazak/dorita980)
* [homebridge-roomba980](https://github.com/steedferns/homebridge-roomba980)
* [homebridge-roomba](https://github.com/umesan/homebridge-roomba)

## Advice

As pointed out in the Readme for [dorita980](https://github.com/koalazak/dorita980), it is wise to disable over-the-air firmware updates for your Roomba.

## Troubleshooting

To be continued...
