# Location (map)

There's a few different devices that provide a location (lat/lng). HD+ displays these devices on a map

[Life360](location-life360/life360+.md)

[OwnTracks](location-owntracks.md)

***

### Google Maps API Key

HD+ does not use a built-in Google Maps API key since there's a limit to how many free requests you can make. However, if you have a location device above it's highly recommended to get your own Google Maps API key and enter it into the app.

See [this page](generate-google-maps-api-key.md) for getting a free Google Maps API key

Once you have it, enter it into the app. How you do this depends on the version of HD+ you have

#### Original Android HD+

* long-click on any Life360 or Owntracks device and hit Edit
* Click on Map Options
* Click on Google Maps API Key and enter your custom maps API key
  * NOTE: this is for the static maps.. I'll add a way to do this for the embedded maps too in a future version
* <img src="../../.gitbook/assets/image (89).png" alt="" data-size="original">![](<../../.gitbook/assets/image (119).png>)

#### New HD+ (Android/iOS/Desktop)

* The easiest way is to create a Hubitat Hub Variable called "GOOGLE\_MAPS\_KEY"

<div align="left"><figure><img src="../../.gitbook/assets/image (260).png" alt="" width="375"><figcaption></figcaption></figure></div>

* Make sure you allow MakerAPI access to this variable

<div align="left"><figure><img src="../../.gitbook/assets/image (261).png" alt="" width="347"><figcaption></figcaption></figure></div>

* HD+ will automatically find and use this
* Alternatively, you can manually set it as well (see [#original-android-hd](./#original-android-hd "mention"))

***
