---
description: Track device location
---

# Location Tracking

Location Tracking will send the device's coordinates (lat/lng) to your Hub. Similar to Apple's "Find My" service or Life360 -- except no 3rd party server involved. The location is only sent to your Hubitat Hub.

**NOTE**: This is an advanced feature and for many the [Presence Tracking](presence-tracking-geofence.md) (Geofence) feature is all you need.&#x20;

* The major difference is Presence Tracking is only interested if you're inside or outside a predefined area (geofence). It will only notify the Hub when that happens.
* Location Tracking passes the actual device location (lat/lng) continuously to the Hub -- allowing the Hub to do more with that location.

## Setting up Location Tracking

1. Install and configure the "[My Location](location-tracking.md#how-it-works-3)" device driver on your Hub
2. In HD+, open More Settings -> Location Tracking
3. Make sure HD+ has all of the permissions it needs.. including Location (allow all the time), Physical activity and unrestricted battery
4. Select your "My Location" device to notify
5. _Optional_ - add [presence support](location-tracking.md#how-it-works-3-1)

![](<../.gitbook/assets/image (59).png>) ![](<../.gitbook/assets/image (60).png>)

permissions needed:\
![](<../.gitbook/assets/image (61).png>) ![](<../.gitbook/assets/image (62).png>)

### Install "My Location" Hubitat driver <a href="#how-it-works-3" id="how-it-works-3"></a>

1. Install the "My Location" device driver on your Hub
   * [@wecoyote5](https://community.hubitat.com/u/wecoyote5) wrote a driver which you can install either from Hubitat Package Manager (it's not there yet but should be soon) or manually from [here](https://raw.githubusercontent.com/wecoyote5/hubitat-MyProjects/main/MyLocation.groovy)
2. Create a new virtual device with "My Location" device type.. give it any name
3. _Optional_ - In the driver preferences, set the presence zone name to "home". It can be set to anything but you'll need to use the same name in HD+\
   ![](<../.gitbook/assets/image (57).png>)
4. Add the new device to MakerAPI so HD+ can see it

### Add Presence (present/not present) support <a href="#how-it-works-3" id="how-it-works-3"></a>

1. Create a new location under Presence Tracking and assign it a name
   * Use the **same name** as you set in the My Location driver (above)

![](<../.gitbook/assets/image (58).png>)

### How it works <a href="#how-it-works-3" id="how-it-works-3"></a>

For now HD+ is relying 100% on Android's Physical activity [API](https://developers.google.com/location-context/activity-recognition/) (side-note: I'm not even sure this is available on all versions of Android). It'll notify HD+ when the user is doing some kind of activity like driving/walking/etc and HD+ will fetch & send the current location to the Hub.

I tested on a Pixel 7 and was a little surprised to see fairly frequent updates being made. It's entirely possible this won't work as well on a Samsung phone but I will keep testing and can adjust the logic from there.

Because I'm relying on the Physical activity API the battery drain should be low. I'll try to add more options which can increase the frequency of updates -- but at the cost of battery life. Either way though, this feature is still a work in progress.

## Disable Location Tracking

* If you want to stop HD+ from doing Location Tracking, you just need to remove the connected Device
  * long-press on Device and select YES to the prompt

<div align="left"><figure><img src="../.gitbook/assets/image (211).png" alt="" width="188"><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/image (213).png" alt="" width="188"><figcaption></figcaption></figure></div>
