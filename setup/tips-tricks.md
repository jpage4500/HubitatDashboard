---
description: General tips to make setting up HD+ easier
---

# Tips / Tricks

### Navigation Drawer

* It can be a little hard to find but there's a navigation drawer that slides out from the left side of the screen. All of the settings for HD+ are in here\
  ![](<../.gitbook/assets/image (5).png>)

### Edit Mode

* EDIT mode lets you rearrange device tiles as well as add new 'virtual' devices such as Date, Radar, Pollen, etc.
* When in EDIT mode, to move tiles around, **press and hold** a device until you see a little tooltip show up. Next, drag the icon to where you want it.
  * NOTE: You can drag a device into a folder. If you don't want the device to go into the folder, keep holding the device down for an extra second or 2 until the folder moves

### Device Options

* Several devices have their own options to customize them.. for example the Thermostat device supports a 'wide' mode and normal mode. The dimmer light device supports 2 different ways of adjusting the brightness.
* Most devices can be customized - background color, icon color and even the icon can be changed. In the same place you can change these colors for all devices of this type, all 'on' or 'off' states for any device and more!
* Some devices can have multiple ways to be displayed. For example, some sensors can be a Temperature sensor, a Humidity sensor, a Contact sensor and more. You can change between the device types in the edit dialog for a device.

### Grouping Devices into a Folder

* The more devices you add into your smart home the harder it'll be to manage all of them. One thing I like to do with multiple devices of the same type (locks, lights, doors, etc) is to group them into a single folder. This will only take up 1 tile but can show multiple device status.
* To quickly groups all devices of a given type into a folder:
  * long-click on a given device and click on Edit
  * click on Group Similar Devices...
  * select type/room or both
    * type will group all devices of the same type (ie: locks) into a folder
    * room will group all devices of the same room (ie: living room) into a folder
    * both will let you group devices of the same type and the same room into a folder (ie: living room lights)

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

### Naming Devices

* HD+ will try to guess the best device type for every Hubitat device. It does this by looking at the device capability, attributes and commands. It also will use the device name/label as well.&#x20;
* For example, if you have a switch with "light" in it, a light device type will be used (vs a more generic switch device type). Other naming hints include:
  * a switch with the text "light" or "lamp" in it will be set as a light device type
  * a switch with the text "fan" in it will be set as a fan device type
  * a switch with the text "outlet" in it will be set as a outlet device type
  * a contact sensor with the text "door" in it will be set as a door device type
  * a contact sensor with the text "window" in it will be set as a window device type
  * a contact sensor with the text "garage" in it will be set as a garage device type
