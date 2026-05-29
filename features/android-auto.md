# Android Auto

If you have a car that supports Android Auto, HD+ will let you control your Hubitat devices from the car screen.

![](<../.gitbook/assets/image (169).png>)![](<../.gitbook/assets/image (142).png>)

![](<../.gitbook/assets/image (194).png>)![](<../.gitbook/assets/image (184).png>)

**Requirements**

* To start, this feature requires a car that supports [Android Auto](https://www.android.com/auto/) and an Android device connected via USB or wirelessly
  * NOTE: There's something _similar_ called Android Automotive or Android Auto OS.. this is when a car runs a full Android OS and can install apps which can be run without a connected phone.
  * I might look into supporting Android Auto OS in the future if there's enough demand
* You'll also need the HD+ app. The production version can be found [here](https://play.google.com/store/apps/details?id=com.jpage4500.hubitat) but today you'll **also** need to subscribe to the [beta version](https://play.google.com/apps/testing/com.jpage4500.hubitat) since I haven't released it to production yet.
  * Make sure you have version 1.0.1984 or greater
  * NOTE: Android Auto **requires** the app to be installed from Google Play so you won't be able to use the sideloaded apk version

**Usage**

* First, make sure you can login to HD+ with your phone and that you have some devices displayed
* Next, connect your phone to your car (USB or wirelessly)
* You should see HD+ show up as an app. Open it!
* By default, HD+ will only show device types that can be controlled or viewed in a car interface -- switches, lights, locks, doors, HSM, thermostats.

**Configuration**

* Once your device has been connected to an Android Auto car, a new setting shows up in HD+ called "Android Auto". This lets you control what devices and what order they should display in.
* To add or remove devices from the list, use the little red "+" button
* You can also re-arrange devices by touching and dragging the little icon on the right side

![](<../.gitbook/assets/image (129).png>)![](<../.gitbook/assets/image (191).png>)



Here's some other notes:

* I'm only supporting (showing) devices that I can display in some way with the very limited options that I have. Generally speaking any kind of switch or sensor.
* By default I'm showing all switches and sensor-type devices but you can configure it using the phone app
* I don't handle every possible device type just yet. I started with the simple ones (lights, switches, valves, locks and similar)
* I'll try to handle any other useful device type one by one.. for example, HSM lets you 'arm' or 'disarm'; The thermostat device type lets you send UP/DOWN commands
* It'll continue to evolve.. my wife's car has Android Auto support but I don't so I won't be using it that often.. so feel free to give feedback or suggestions!
* In order to use an app with Android Auto you **must** be using the Google Play version. This is something built-into Android Auto

**Links**

* [HD+ Hubitat Android Auto Support](https://community.hubitat.com/t/hd-android-auto-support/118392)
* [HD+ Hubitat Support Page](https://community.hubitat.com/t/release-hd-android-dashboard/41674) -- I always post new versions here and I'll _try_ to post anything auto related to this thread too but just in case...

## Future Plans

Google supports a 'tabbed' UI navigation but it's not available until V6 of the car API. I can't even test with it. But, I'll be ready to add it when it is.

![](<../.gitbook/assets/image (138).png>)



<br>
