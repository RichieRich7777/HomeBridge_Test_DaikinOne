# Homebridge Daikin One+ Thermostat Plugin

Homebridge plugin to control a Daikin One+ Thermostat.

The plugin connects to the Daikin One+ API to retrieve all devices on your account and adds any thermostats found to Homebridge.

In addition to retrieving and setting the thermostat's current temperature, it will also retrieve the current relative humidity 
and allow you to set the desired humidity level.

If your Daikin system reports such values, the plugin will also create separate Air Quality and Indoor/Outdoor Humidity sensors.

## Installation
If you are new to Homebridge, please first read the [Homebridge](https://homebridge.io) [documentation](https://github.com/homebridge/homebridge/wiki) and installation instructions before proceeding.

If you have installed the [Homebridge Config UI](https://github.com/oznu/homebridge-config-ui-x), you can intall this plugin by going to the `Plugins` tab and searching for `homebridge-testdaikin-oneplus` and installing it.

If you prefer to install `homebridge-testdaikin-oneplus` from the command line, you can do so by executing:

```sh
sudo npm install -g homebridge-testdaikin-oneplus
```

## Homebridge Config

The easiest way to configure this plugin is via [Homebridge Config UI X](https://github.com/oznu/homebridge-config-ui-x).

```javascript
"platforms": [
  {
    "platform": "DaikinOnePlus",
    "name": "Daikin One+",        // Required. The name of the thermostat. Can be anything.
    "user": "any@email.address",  // Required. The email of your Daikin One+ account.
    "password": "password",       // Required.
    "refreshInterval": 10,        // Required. The interval (in seconds) at which the plugin should get current values from the Daikin API.
    "includeDeviceName": false,   // Required. Should the default sensor names start with the thermostat name (as configured in the thermostat).
  }
]
```

## Acknowledgements
The Daikin API requests and parsing of the results is based on the [daikinskyport](https://github.com/apetrycki/daikinskyport) repo by apetrycki.
