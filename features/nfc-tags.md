---
description: Automate hub actions using NFC Tags
---

# NFC Tags

The dashboard supports scanning NFC tags to perform actions

For example,

* scan a tag to enable/disable your home security
* scan a tag to turn on/off lights

### Getting Started

It's easy to get started.. here's what you'll need:

* NFC Tags.. super cheap. I bought [20 for $10](https://www.amazon.com/gp/product/B09337ZYW8) - just search Amazon for "NFC tags". I'm still learning the various formats but you should be good with anything that says "NTAG 215" on it.
* An NFC Tag writer app. [NFC Tools](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc\&hl=en_US\&gl=US) is free

### Which device to command?

The next step is figuring out which device to perform the action on. This can be any Hubitat device or even a virtual device tile such as an image tile.

Figure out the device ID of the device you want to command. For Hubitat devices, you can find the device ID by looking at the hub's [device list](http://hubitat.local/device/list) page -> clicking on the device you want to control and looking at the URL in your browser. The device ID is the last value ("66" in the example below)\
![](<../.gitbook/assets/image (93).png>)

### What action to perform?

What you want to do when scanning a particular NFC tag? There's currently 2 options:

* view the device; this behaves the same as if you were to click on a device/tile in the app. If it's an actionable device a prompt will be displayed (on/off) or if it's another type of device (ie: image) it'll open the tile full-screen
* toggle the device state silently; this only works for devices that can be toggled (lights/switches/valves/locks); no UI is displayed - the device's state is toggled on the hub

### Create the custom URL

When you know the device ID and action - creating the custom URL syntax is easy. The URL format is: "hd://\<command>/\<device id>"

* \<command> can be one of "view" or "toggle"
  * "view" will show you the device as thought you clicked on it in the app. If it's a device that can be toggled, you'll see an on/off prompt
  * "toggle" will silently toggle the state of the device - from on -> off - without prompting
* \<device id> is the hubitat hub's device ID of the device you want to control.

#### Example URL's:

* **hd://view/66** -> will show the on/off prompt for device ID: 66\
  ![](<../.gitbook/assets/image (196).png>)
* **hd://toggle/66** -> will toggle the device state silently\
  ![](<../.gitbook/assets/image (167).png>)

### Writing the NFC Tag

* Open the NFC Tools app
* Under the WRITE tab, click on "Add a record"
  * NOTE: If a record already exists from a previous tag you created, you can edit it instead or delete it
* Click Custom URL / URI
* Enter the URL you created in the above step. It MUST start with "hd://" to work
* Click Write button
* Place NFC tag up against the back of your phone (my S20 requires the tag to be in the middle of the device.. other devices might have the NFC reader in a different place)

![](<../.gitbook/assets/image (190).png>)![](<../.gitbook/assets/image (174).png>)![](<../.gitbook/assets/image (122).png>)![](<../.gitbook/assets/image (121).png>)

### Test the result

* Once the NFC tag is written, you can close NFC Tools app. Now, anytime you place the NFC tag up against your device it should either send the command or open a prompt.
* NOTE: NFC doesn't work when the device is locked. The Hubitat dashboard does NOT have to be running but the device does have to be unlocked first.
