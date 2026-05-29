# Login

## Automatic Login

* Click on "Discover Hub" button and if all goes well - you'll be logged in and will see all of your devices!
  * Note: You will need to be on the same network as your Hubitat Hub for this to work

{% embed url="https://youtu.be/ZOPO_ORiY-c" %}

## Manual Login

* If the Automatic Login doesn't work, you can manually enter your Hub's details. Hit the Manual button to show the IP address field.
  * Note: You will need to be on the same network as your Hubitat Hub for this to work
  * HD+ will attempt to fetch the MakerAPI app ID automatically

<figure><img src="../../.gitbook/assets/image (207).png" alt=""><figcaption></figcaption></figure>

## Advanced Login

* If the Automatic or Manual logins don't work - you can still login but will need to first get some information from the Hubitat's MakerAPI page.
* Navigate to your Hub's webpage (typically [hubitat.local](http://hubitat.local))
* Click on Apps on the navigation bar and click on the MakerAPI app\
  ![](<../../.gitbook/assets/image (100).png>)
* When on the MakerAPI apps page, look at the URL in your browser. It should look like this: http://\[HUB-IP]/installedapp/configure/**38**/mainPage. The "38" is the app ID. Enter this into the App ID field in the app\
  \
  ![](<../../.gitbook/assets/image (144).png>)
* Scroll down and look for "access-token". Enter this in the Access Token field for the app<img src="../../.gitbook/assets/image (95).png" alt="" data-size="original">
*   If you want to use the app remotely (cloud support), scroll down further and look for a URL that starts with "cloud.hubitat.com". The value after /api/ is the Cloud token. Enter this into the Cloud token field of the app

    ![](<../../.gitbook/assets/image (125).png>)

<figure><img src="../../.gitbook/assets/image (208).png" alt=""><figcaption></figcaption></figure>

## Troubleshooting Logging In

If you're not able to login, here's some troubleshooting steps:

* If you have enabled Hub Security (username/password) on your Hub, the app should detect this and prompt you to login. However, if this isn't working you might want to try disabling Hub Security temporarily just to login to the app.
* The "Discover Hub" button uses UPnP to discover your hub on the network. UPnP isn't enabled on all networks and the app only waits a few seconds to discover the hub before timing-out and showing the IP address field. You can show it at any time by hitting the "Manual Entry" button. Enter your Hubitat Hub's IP address here and hit Login
  * The app does 2 things when you hit Login:
  * fetch the apps list page: http://HUB.IP/installedapp/list and look for "Maker API" app ID
  * fetch the Maker API settings page: http://HUB.IP/installedapp/configure/APP.ID/mainPage and look for access token ?access\_token=ACCESS\_TOKEN and cloud token https://cloud.hubitat.com/api/CLOUD.TOKEN/apps
* The automatic login process above could fail on future Hubitat Hub updates. Just report the issue on the Hubitat forums or send me a device log and I'll get it fixed!
