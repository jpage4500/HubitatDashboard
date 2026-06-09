---
description: Adding a homescreen widget
---

# Widgets

## Add a Widget

This will vary by which Android OS and homescreen launcher you're using.

* Most launchers allow you to add a new widget by long-pressing on an empty space on your Android homescreen.
* In the widget picker, find Hubitat Dashboard and the 1x1 widget
* Long-press on the widget and while holding down drag the icon to where you want it on the homescreen
* When you let go, you'll see a widget configuration dialog
* Select the device you want to use for the widget and any other options you want for this widget and hit "CREATE WIDGET" to add it
* Options:
  * **Prompt to Toggle**: enable to prompt before toggling any device.
    * For example, if the device is a light/switch and this option is enabled, you'll be prompted to turn the light ON/OFF. If disabled, the light will be automatically toggled w/out prompting
  * **Refresh Rate**: How often you'd like the app to refresh the state of this device. If set to 0, this device will never automatically refresh. The more often a device state is refreshed, the more battery is used
  * **Ignore Battery Optimizations**: Enable this option to make the refresh rate more accurate. By default, Android OS will try to optimize how much an app 'wakes' to do work so the Refresh rate selected will sometimes be delayed (outside of the control of this app)

![](<../.gitbook/assets/image (180).png>) ![](<../.gitbook/assets/image (171).png>) ![](<../.gitbook/assets/image (178).png>) ![](<../.gitbook/assets/image (104).png>)

## ![](<../.gitbook/assets/image (98).png>)![](<../.gitbook/assets/image (104).png>)

## Update a Widget

Once a widget is created, you can edit it from the Dashboard app

* Nav Menu -> More Settings -> Configure Widgets (only shows up if you have 1 or more widgets configured)
* Select the widget you want to edit and hit OK

![](<../.gitbook/assets/image (72).png>) ![](<../.gitbook/assets/image (137).png>)

## Remove a Widget

Removing a widget needs to be done via the Android homescreen

* long-press on the widget to remove and drag to "Remove" label (will vary by OS)

![](<../.gitbook/assets/image (140).png>)
