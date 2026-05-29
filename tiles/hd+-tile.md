---
description: Create a variety of custom tiles on HD+ without typing on your phone/tablet
---

# HD+ Tile

## Background

There's a lot of device types that HD+ supports which aren't Hubitat apps/drivers. For example, you can create a Calendar tile on your dashboard or an animated radar image.

You can add these tiles directly in HD+ by going into Edit mode -> click on the "+" sign for Add Tile

<div align="left"><figure><img src="../.gitbook/assets/image (36).png" alt="" width="188"><figcaption></figcaption></figure></div>

**HOWEVER**, entering a URL on a phone or tablet isn't the easiest thing to do!

## Solution

An easier way to create these custom device type tiles is to install the "HD+ Tile" device on your Hubitat and set it up on the Hubitat instead. This device supports most of the HD+ tiles that can be added directly on the device and includes Calendar, Image, Stock Tracker, Video, Radar and more

## INSTALL HD+ TILE DRIVER <a href="#install-hd-tile-driver-2" id="install-hd-tile-driver-2"></a>

* The easiest way is to use [Hubitat Package Manager](https://hubitatpackagemanager.hubitatcommunity.com/) -- select install -> keyword search -> "HD+ Tile"

<div align="left"><figure><img src="../.gitbook/assets/image (37).png" alt="" width="375"><figcaption></figcaption></figure></div>

* Next, for **EACH** device you want to create, create a new virtual device in Hubitat -> Devices page, give it any name and select "HD+ Tile" as the type:

![](<../.gitbook/assets/image (38).png>)<br>

* In the driver page pick a device type (ie: image/video/calendar/etc) and enter a URL for it. You can also enter a refresh rate (ie: 30 secs)
  * see [Examples](hd+-tile.md#examples) below
* Make sure to give the tile a name

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

## Add Tile to MakerAPI

* Add the new tile to [MakerAPI](hd+-tile.md#add-tile-to-makerapi) so HD+ will see it the next time is syncs

## Examples

* **Image URL**
  * animated [radar](https://cdn.star.nesdis.noaa.gov/GOES16/ABI/SECTOR/se/Sandwich/GOES16-SE-Sandwich-600x600.gif)
  * this [site](https://www.star.nesdis.noaa.gov/GOES/index.php) has some good radar images
* **Video URL**
  * stream video from your local camera (ie: `rtsp://user:pass@192.168.0.70:554/h264Preview_01_sub`)
* **Web URL**
  * any website (ie: [`http://windy.com`](http://windy.com))
  *   embedded HTML snippet

      ```
      <iframe width=\"1200\" height=\"1200\" src=\"https://embed.windy.com/embed2.html?lat=35.136&lon=-80.767&detailLat=35.136&detailLon=-80.767&width=600&height=600&zoom=5&level=surface&overlay=wind&product=ecmwf&menu=&message=true&marker=&calendar=now&pressure=&type=map&location=coordinates&detail=&metricWind=default&metricTemp=default&radarRange=-1\" frameborder=\"0\"></iframe>
      ```
* **Calendar**
  * Enter 1 or more iCal URL's separated by a comma
  * You can find an iCal URL in Google Calendar\
    ![](<../.gitbook/assets/image (41).png>)
  * Most sports teams offer iCal URL's
* **Pollen Count**
  * Enter your zip code in the URL field
* **Radar**
  * Enter your zip code in the URL field
* **Stock Symbol**
  * Enter 1 or more stock symbols in the URL field
  * Example: `AAPL,PZZA,RBLX`
* **Dad Jokes**
  * The URL field is ignored so just enter anything here
* **Device Activity**
  * Used by HD+ to track your device activity (still/driving/walking/running/etc)
  * URL field is ignored
  * status1 field is set to one of: \[still/driving/walking/running/unknown]
  * status2 field is set to % confidence that OS believes this is the activity you're doing
  * see [device-activity.md](device-activity.md "mention")for more details



The end result is every device running HD+ will now have a new image/video/etc tile

[![image](https://community.hubitat.com/uploads/default/optimized/3X/4/8/48bb708471ccde049d4e5dc552c9291a1422f04e_2_345x231.jpeg)](https://community.hubitat.com/uploads/default/original/3X/4/8/48bb708471ccde049d4e5dc552c9291a1422f04e.jpeg)

