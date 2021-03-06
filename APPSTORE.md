# Control Xiaomi Mi Home Wi-Fi devices
Use Homey to control Xiaomi Mi Home devices (the Mi Home Ecosystem is also branded as MiJia). Currently Xiaomi does not officialy support controlling most of it's devices from outside the Mi Home app with the exception of Yeelights. Yeelights can be added to Homey quite easy but for all other devices additional steps are needed that require some technical knowledge setting up. These steps are described but Xiaomi can make changes to it's eco system at any time resulting in devices that can not be added or controlled by Homey anymore.

This app uses an unofficial library called the [miIO Device Library](https://github.com/aholstenson/miio) for communication with those devices which lack official support for controlling externally, credits go out to the author of this library. This Homey app only adds support for the devices that can be controlled directly through Wi-Fi (there is another app for directly controlling Xiaomi ZigBee sensors).

## Supported devices
Below is a list of supported devices and devices. Post a comment in the [support topic](https://forum.athom.com/discussion/3295/) if you would like to see support for a specific device, some devices might already be supported by the miio library but just need to be implemented. For devices not yet support by the miio library you need technical knowledge to discover the device properties yourself as described [here](https://github.com/aholstenson/miio/blob/master/docs/missing-devices.md).
* Yeelights: Bulbs Wi-Fi (tested), LED strips (tested), Bedside Lamp II (tested), Ceiling Lights (tested)
* Xiaomi Philips: Light Bulbs (untested), Eyecare Lamp 2 (untested)
* Xiaomi Robot Vacuum Cleaner (tested)
* Xiaomi Air Purifiers 2, 2S and Pro (tested)
* Xiamomi Humidifier (tested)
* Xiaomi Single Power Plug and Power Strip WiFi version (tested)
* Xiaomi PM2.5 Air Monitor (tested)
* Xiaomi Gateway Light - alarm not supported yet and subdevices are supported directly with the Xiaomi ZigBee app (tested)

## Support topic
For support please use the official support topic on the forum [here](https://forum.athom.com/discussion/3295/).

## Adding Yeelights
This Homey app supports direct control for Yeelights. Before being able to add your Yeelights as devices in Homey you will need to enable the "Developer Mode" or "LAN control" in the official Yeelight app. You can do this by using the official Yeelight app on your smartphone (not the Xiaomi Mi Home app but the actual Yeelight app). In this app go into the settings of your bulb and you will see a menu item called Developer Mode. This contains a toggle to enable the developer mode. After enabling this the Homey app will be able to autodiscover your bulb when adding it as new device.

## Adding miIO devices
For Homey to be able to communicate with devices over the miIO protocol a unique device token needs to be obtained. Technical knowledge is needed for retrieving these tokens. If your are not to tech-savvy using this app for any other devices than the Yeelights might be challenging. See the instructions [here](https://github.com/jghaanstra/com.xiaomi-miio/blob/master/docs/obtain_token.md) on retrieving device tokens.

## Changelog
### 2018-04-06 -- v2.6.3
* UPDATE: changed device class from Xiaomi Gateway to light (repair if you want to use the light flow cards)
* NEW: added trigger card for changes in luminance for Xiaomi Gateway
* FIX: fixed an error with setting the light temperature for the Philips Bulbs
