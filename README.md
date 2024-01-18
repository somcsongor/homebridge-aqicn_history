# Homebridge-airnow
[![NPM Version](https://img.shields.io/npm/v/homebridge-airnow.svg)](https://www.npmjs.com/package/homebridge-airnow)

Air Quality Index Sensor Plugin for [Homebridge](https://github.com/nfarina/homebridge)
This plugin allows you to monitor your current AirQuality from HomeKit and Siri.
This is based on [Homebridge-airnow]https://github.com/ToddGreenfield/homebridge-airnow

Currently supports two AQI Services:
1. [Aqicn](https://www.aqicn.org) which has international support, provided by the [World Air Quality Index Project](http://waqi.info/).

Depending on where exactly you would like to monitor AQI, one service may be more appropriate than the other.

## Installation
1. Install homebridge using: `npm install -g homebridge`
2. Install this plugin using: `npm install -g homebridge-aqicn_history`
3. Update your configuration file like the example below.
4. Ensure you have Aqicn.org API account to use that web service and have a valid API_KEY. 
For assistance visit http://aqicn.org/data-platform/token/#/.


This plugin will create an AirQualitySensor element. The Home app works well, but the Eve app seems to show more measurements. Measurements retrieved are PM2.5, PM10, NO2, SO2, CO & O3 
## Configuration
Example config.json:

```js
"accessories": [
	{
		"accessory": "airnow",
		"name": "Air quality",
		"provider": "aqucn",
		"aqicn_api": "XXXXXX",
		"aqicn_station": "A402109",
		"polling": "10"
	}
],
```



## Explanation:

Field           		| Description
------------------------|------------
**accessory**   		| Required - Must be "airnow" (all lowercase).
**name**        		| Required - Name override for logging.
**provider**       		| Required - Name of the AQI provider service. Valid options is: aqicn
**aqicn_api** 			| Optional - Required for Aqicn.org. YOUR API key from Aqicn.org.
**aqicn_station**			| Required -Used for Aqicn.org - A valid station @code from http://aqicn.org/city/all/ OR defaults to 'here' which will use Geolocation based on your IP.
**polling**				| Optional - Poll interval. Default is 0 minute, which is OFF or no polling.
