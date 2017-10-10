homebridge-roomba690
=========

**This has not yet been uploaded to npm!**

This Homebridge plugin adds support for the Roomba 690.

It also adds a BatteryService, allowing you to check on the charging status of the 690.

## Features

* Start / stop Roomba *Hey Siri, turn on the Roomba*
* Check on/off status *Hey Siri, is the Roomba on?*
* Check charging status *Hey Siri, is the Roomba charging?*
* Check battery status *Hey Siri, is the Roomba charged?*

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

## Why another Roomba plugin?

Unfortunately, the [homebridge-roomba980](https://github.com/steedferns/homebridge-roomba980) or [homebridge-roomba](https://github.com/umesan/homebridge-roomba) plugins don't work with the Roomba 690.

The 690 has a limited feature set in comparison to the higher-end models, a consequence being that it doesn't support some of the methods that these two plugins use from the dorita980 kit.

This plugin uses methods that the 690 does support in order to bring Homebridge support to your Roomba.

## Logging and Troubleshooting

Logging is fairly verbose and should assist you in troubleshooting any issues. Look in your usual Homebridge logs.

Make sure that the plugin is actually being loaded:

```
Loaded plugin: homebridge-roomba690
Registering accessory 'homebridge-roomba690.Roomba690'
```

Verify that your configuration is correct:

```
[Roomba] Initializing Roomba690 accessory...
[Roomba] Initialised Roomba with Name: [Roomba] Hostname: [192.168.0.239] BLID: [XXXXXXXXXXXX] Model: [690]
[Roomba] Services requested
[Roomba] Reporting that we support AccessoryInformation, SwitchService and BatteryService
```

Whenever you request information, you should see activity in the logs

*Hey Siri, is the Roomba on?*

```
[Roomba] Power state requested for Roomba
[Roomba] Connected to Roomba
[Roomba] Status is [charge]
[Roomba] Roomba is not running
```

*Hey Siri, is the Roomba battery charged?*

```
[Roomba] Battery level requested for Roomba
[Roomba] Connected
[Roomba] Roomba battery level [100]
```
