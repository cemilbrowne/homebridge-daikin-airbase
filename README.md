<p align="center">
    <img src="documentation/logo.png" width="200" alt="Daikin Airbase logo">
</p>

# Homebridge Daikin Airbase

A Homebridge plugin providing support for the **Daikin Airbase** WiFi module (BRP15B61).

It allows to turn on / off the aircon, set it to cool / heat / auto mode (when supported), change the target temperature and the fan speed.

<p align="center">
    <img src="documentation/change-cooler.gif" height="400" alt="Animated gif showing the Daikin aircon in the home app, setting it to cool">
    &nbsp;
    <img src="documentation/change-fan-setting.gif" height="400" alt="Animated gif showing the Daikin aircon in the home app, changing the fan speed">
</p>

# Requirements

-   **Node** version 11 or above (verify with `node --version`).
-   **Homebridge** version 0.4.0 or above.

# Installation

1. Install homebridge using:

```sh
npm install -g homebridge
```

2. Install the plugin using:

```sh
npm install -g homebridge-daikin-airbase
```

3. Update your configuration file. See bellow for a sample.

> **Note:** it is also possible to install this plugin in a local `npm` package instead using the homebridge option `--plugin-path`.

# Configuration

## General settings

To configure `homebridge-daikin-airbase`, add the `DaikinAirbase` platform to the `platforms` section of your homebridge's `config.js` file:

```json
{
    "bridge": { "...": "..." },

    "description": "...",

    "platforms": [
        {
            "platform": "DaikinAirbase",
            "name": "My Daikin Airbase Hub",

            "hostname": "<e.g. 192.168.1.10>"
        }
    ]
}
```

The platform can be configured with the following parameters:

| Parameter  | Type   | Default | Note                                                                                                       |
| ---------- | ------ | ------- | ---------------------------------------------------------------------------------------------------------- |
| `hostname` | String | `null`  | **Required** - The hostname on your local network of the Daikin Airbase module (do not include `http://`). |

# Limitation

This plugin does not support setting the aircon into **Dry** or **Fan** mode as these are not supported natively by Homekit (they cannot be mapped to a control in the Home app).

# Contribute

Please feel free to contribute to this plugin by adding support for new device types, implementing new features or fixing bugs. Pull requests are welcome.
