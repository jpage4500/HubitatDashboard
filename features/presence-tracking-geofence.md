---
description: More reliable location tracking over the native Hubitat app
---

# Presence Tracking (Geofence)

### Background

Geofencing is where an app can register a location (coordinates + radius) with the Android OS. Then, whenever the device ENTERS or EXITS that location - the app gets notified. It's supposed to be efficient/battery friendly because the app doesn't have to do any work in the background.

In a smart home setup, it's important that these notifications are timely as they can be used to put your Hubitat into 'away' mode - which you can then use to arm or disarm security.

The native [Hubitat app](https://play.google.com/store/apps/details?id=com.hubitat.app\&hl=en_US\&gl=US) already supports geofencing. It will create a new 'mobile app' device on your Hub and then set that device to 'present' or 'not present' depending on your phone's location.

The main reason I wanted to add geofencing support to this app is to supplement the native Hubitat Android app which hasn't been very reliable of late. After spending a good week working on this feature I can see why.. **Samsung devices do NOT deliver reliable geofence notifications**!

From my testing Samsung devices will delay these ENTER/EXIT notifications for a long time to the point of being unreliable.

### Making Geofence more reliable

So, the next question is - what can be done to make these more reliable? And how to do this without using too much battery?

There are apps like [Life360](https://play.google.com/store/apps/details?id=com.life360.android.safetymapd\&hl=en_US\&gl=US) which are very reliable but you'll also notice how they display a system notification seemingly all the time. This is necessary in Android for an app to do any kind of work in the background.

I want to try and find a decent balance of being reliable but also not constantly working in the background (draining battery). In addition to adding a geofence, I'm also listening to several different system events including connection changes (ie: WIFI -> Mobile) and physical activity states (driving) and checking the current location.

### Presence Tracking (Geofencing)

This feature is only available if your device has cellular support (ie: not a WIFI only tablet). You can enable it under More Options -> Presence Tracking.

* **Location**
  * The first time you select Location it'll prompt you to grant Background Location permission. This is required for geofencing.
  * It'll also prompt for Activity Tracking but this is optional. Activity Tracking permission will notify the app when the OS _thinks_ your device is moving and HD+ will use this to supplement the geofencing
* **Device**: Select any Hubitat device you want to update when your phone goes in and out of the geofence. You can select any 'switch' capable device or the "Mobile App Device" which is created automatically by the native Hubitat app.
  * NOTE: This is optional; If you don't select a device to update you can still use this feature with 'Show Notifications' to test the reliability of geofence notifications
  * NOTE: Remember to add the device to MakerAPI so it's visible to the app
* **Ignore Battery Optimizations:** This allows HD+ to do more work in the background and is recommended
* **Physical Activity Permission:** Activity Tracking permission will notify the app when the OS _thinks_ your device is moving and HD+ will use this to supplement the geofencing
* **Show Notifications**: Enable this to be alerted with a system notification when your device enters or exits the selected location
* **Monitor Location**: Enable the feature; This is just a quick way to disable location tracking in the app without having to delete the locations you've already setup

<figure><img src="../.gitbook/assets/image (215).png" alt=""><figcaption></figcaption></figure>

### Notes

* I've been testing this feature on a Samsung device for several months now and it's been very reliable. I typically get notified a few seconds after leaving the geofence area
* If you're happy with the results, disable geofencing on the native Hubitat app so you don't have 2 apps working in the background<br>
