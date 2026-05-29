# Support / Feedback

## Debug Mode

Putting the app into debug mode increases the logging - so if you were to re-create an issue and send me the logs I'll have a much better chance of figuring out what's going on.

* Open the navigation menu
* Click About
* Enable Debug Mode toggle switch
* Now, reproduce any issue and [send the logs](./#sending-a-device-log)

<div align="left"><figure><img src="../../.gitbook/assets/image (23).png" alt="" width="188"><figcaption></figcaption></figure></div>

## Sending a device log

**The best way to request support for your device(s) is to send me the app's device log** and include what you're looking to support/change. A screenshot might also be helpful if you can send one since I won't always be able to reproduce what you're seeing.

* Open the navigation drawer (swipe right from the left edge of the screen)&#x20;
* Click on **About**
* Click on **Support / Feedback**

## Hubitat Support Forums

Another great resource for support is the Hubitat support forums. [This thread](https://community.hubitat.com/t/release-hubitat-dashboard-android-dashboard-app/41674) is just for the HD+ app

{% embed url="https://community.hubitat.com/t/release-hubitat-dashboard-android-dashboard-app/41674" %}

## New Device Support

If you have a device that's supported in the Hubitat Hub but isn't supported in the Dashboard, send me a device log and I'll do my best to try and support it. Alternatively, you can send me the device JSON that the app gets from MakerAPI.

* Open the MakerAPI app page
  * Go to hubitat's App's page (try [http://hubitat.local/installedapp/list](http://hubitat.local/installedapp/list))
  * Find and click on MakerAPI
* Scroll down to the link "Get All Devices with Full Details" and click on it
  * ![](<../../.gitbook/assets/image (68).png>)
  * Copy the resulting text and paste it into this page: [https://jsonformatter.org/](https://jsonformatter.org/) and hit "Format/Beautify"
  * <img src="../../.gitbook/assets/image (94).png" alt="" data-size="original">
  * Find the device you're interested in supporting and send it to me at joe.page.software@gmail.com

## Manually Getting a Device Log

If for some reason you're not able to send device logs from the app itself, here's how you can get device logs manually.

Note this will vary by device and your PC's OS (Windows/Mac/etc). Typically it involves

* Installing Android ADB tools
* Enabling debug mode on your device and enabling 'USB mode'
* Connecting your device to your PC via USB
* Accept authorization prompt that shows up on your device
* running the command:
  * `adb logcat -v threadtime > /tmp/devicelog.txt`
* sending the logs via email

There's some guides out there on the first step so I'll just link to them instead:

* [https://www.hexnode.com/mobile-device-management/help/obtain-android-device-logs-using-windows-and-mac/](https://www.hexnode.com/mobile-device-management/help/obtain-android-device-logs-using-windows-and-mac/)
* [https://www.xda-developers.com/install-adb-windows-macos-linux/](https://www.xda-developers.com/install-adb-windows-macos-linux/)
