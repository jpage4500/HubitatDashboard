---
description: Support for various Hubitat devices
---

# Hubitat Devices

HD+ will try to automatically display every Hubitat device in the best way possible. Each Hubitat device is assigned a 'device type' by default.

This page describes many of the ways HD+ will display different devices.

* If you want to change the default device type. See this [page](../../features/change-device-type.md) for details
* If you want me to add support for a device or change how it's displayed - please request it in the Hubitat Support Forums [here](https://community.hubitat.com/t/release-hd-android-dashboard/41674)

## Built-in Device Types

NOTE: for capabilities, see this [Hubitat page](https://docs2.hubitat.com/en/developer/driver/capability-list)

#### Lock

* requires capability Lock
* supports commands lock and unlock
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (220).png" alt="" width="171"><figcaption></figcaption></figure></div>

#### Door

* requires capability ContactSensor or DoorControl
  * NOTE: will be used by default if contact sensor and "door" is in the device name
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (221).png" alt="" width="167"><figcaption></figcaption></figure></div>

#### Garage Door

* requires capability ContactSensor or GarageDoorControl
  * NOTE: will be used by default if contact sensor and "garage" is in the device name
* sends commands open and close (GarageDoorControl only)
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (222).png" alt="" width="167"><figcaption></figcaption></figure></div>

#### Light

* requires capability Light
* sends commands on and off
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (226).png" alt="" width="170"><figcaption></figcaption></figure></div>

#### Dimmable Light

* requires capability SwitchLevel
* sends commands on, off, setLevel
* optional display modes:
  * Slider Control - show a slider under the light for brightness control on main dashboard
  * Circular Control - show a ring indicating brightness around the light
  * Hide Dimmer Controls - don't show brightness on the light
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (227).png" alt="" width="188"><figcaption></figcaption></figure></div>
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (228).png" alt="" width="188"><figcaption></figcaption></figure></div>

#### Dimmable RGB Light

* requires capability ColorControl (color), ColorTemperature (color temp), SwitchLevel (brightness)
* sends commands on, off, setLevel, setColor
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (229).png" alt="" width="188"><figcaption></figcaption></figure></div>

#### Fan

* requires capability FanControl
* sends commands on and off
* can also control fan speed and light if suppored by device
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (223).png" alt="" width="188"><figcaption></figcaption></figure></div>

#### Light Sensor

* requires capability [IlluminanceMeasurement](https://docs2.hubitat.com/en/developer/driver/capability-list#illuminancemeasurement)
* displays the `illuminance` value
* optionally can display a background that corresponds to the illuminance value (lighter colors = higher value) - enable "Custom Background" in device edit page
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (218).png" alt="" width="375"><figcaption></figcaption></figure></div>
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (219).png" alt="" width="188"><figcaption></figcaption></figure></div>

#### Variable Boolean

* requires capability Variable and value `variable` = true/false
*

    <div align="left"><figure><img src="../../.gitbook/assets/image (230).png" alt="" width="169"><figcaption></figcaption></figure></div>

#### Thermostat

* requires [thermostat](https://docs2.hubitat.com/en/developer/driver/capability-list#thermostat) capability
* see [Thermostat](thermostat.md) page for options
