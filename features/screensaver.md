---
description: Automatically darken screen when idle and wake when motion detected
---

# Screensaver

This option is an alternative to the [keep-screen-on.md](keep-screen-on.md "mention")feature. While "Stay Awake" keeps the device's screen ON during specified hours, Screensaver instead will keep the screen awake all of the time and darken it after a given idle time. Then, the screen will wake automatically either based on a given device's activity (ie: door opened) or with motion detected using the device's camera.

Note - when the screen is darkened you can always tap it to return to the app

![](<../.gitbook/assets/image (65).png>)

* **Idle Time** - Number of minutes the app is idle before showing the screensaver (darken the screen)
* **Wake On Motion** - enable to use the device's front camera to detect motion and wake the screen
* **Wake on device activity** - select a Hubitat device to watch for activity and wake the device
  * For example, the front door lock could be used to wake the app when locked/unlocked
* **Test Screensaver** - this lets you test the screensaver and the options you selected



**NOTE**: HD+ will darken the screen as much as possible but it can't fully turn it off. The reason the screen has to stay on is to keep receiving events from the Hubitat Hub
