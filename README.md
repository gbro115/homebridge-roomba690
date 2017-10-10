homebridge-roomba690
=========

Adds support for the Roomba 690 to Homebridge.

## Installation

`npm install -g homebridge-roomba690`

## Homebridge configuration

Add to your config.json:

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

## Credits

This code was built upon the work in the following projects:

* [dorita980](https://github.com/koalazak/dorita980)
* [homebridge-roomba980](https://github.com/steedferns/homebridge-roomba980)
* [homebridge-roomba](https://github.com/umesan/homebridge-roomba)

## Advice

As pointed out in the Readme for [dorita980](https://github.com/koalazak/dorita980), it is wise to disable over-the-air firmware updates for your Roomba.

## Troubleshooting

To be continued...
