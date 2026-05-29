# Cloud Mode

Cloud mode refers to connecting to your Hubitat remotely (via the cloud) and not via the local IP address.

Generally speaking, local mode is superior to cloud mode because while in local mode the app connects to a websocket that's not available remotely. This websocket allows the Hub to 'push' device changes to the app instantly - no polling needed.

## Enabling Cloud Mode (the easy way)

* On initial login, the app will prompt you to enable cloud mode detection.&#x20;
* Selecting **YES** here will prompt you to enable location permission for the app
* Grant the app location permission and the app will detect the Wifi Access Point you're currently connected to and use that for the future to determine local vs cloud mode.

![image](https://lh4.googleusercontent.com/alZ0bk0tjuhdlVMMiSbv1U-4GHYpUXCrVpr_18EYTaIac2WUt01O259iPjeR1No8Lf6J-En6UF5zNdRk5cO8dVR3M9KeadYemN1AzRtbtri7y23QKZS1UZgytWFRBpv8CJJSs5kb=s0)

## Cloud Mode Settings

* You can view or edit cloud mode details by clicking on More Options -> Cloud Mode
* Cloud mode works by saving the SSID (network access point name) when you first login. Whenever the network changes the app compares the current SSID with the saved SSID..
  * If they're the same, you're on the same network as the Hub and it connects via local IP address.
  * If they're not the same, the app uses cloud.hubitat.com URL to connect to your hub
* NOTE: Location permission is required because newer versions of Android do not allow apps to know the SSID name (access point name) without location permission

![](<../.gitbook/assets/image (78).png>)

## Technical Details

Here's how the app determines to use local or cloud mode:

* Prerequisite: cloud mode = "Auto" (app will determine)
* Prerequisite: cloud token must be set
* If **wifi and ethernet are not connected**, app will use cloud mode
* If **location permission IS granted** and you have a WiFi Access Point (SSID) set, app will compare the current SSID and will use cloud mode if they don't match
  * example: if your device is connected to a wifi access point called "Family Wifi" and that's what's set in the WiFi Access Point setting - the app will use local mode. Otherwise, cloud mode
* Lastly, the app will try to get the device's local IP address. If the first 3 octets match the Hub's IP address the app will use local mode. Otherwise, cloud mode
  * example: your local device is 192.168.0.100 and the Hub is 192.168.0.25 = local mode is used
  * this isn't as reliable as using the SSID however since multiple networks can have the same first 3 octets.. so it's not a guarantee you're on the same network as the hub.. just a best guess.

Note also that the app performs this 'cloud' check in only a couple of cases:

* when the app is launched or brought to the foreground
* when the app is notified of a network connection change (ie: wifi connected, disconnected)

So, in summary the best way to ensure the app switches accurately between local and cloud mode:

* make sure location permission is granted to the Hubitat Dashboard app
* make sure the WiFi Access Point is set to the same network as your Hubitat Hub.
  * You can get this value by using the "Get Current SSID" button in the screenshot below.

![](<../.gitbook/assets/image (201).png>)
