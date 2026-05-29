---
description: Track device activity
---

# Device Activity

A device activity tile displays the current device activity - which can be one of the following states:

* IN\_VEHICLE
* ON\_BICYCLE&#x20;
* ON\_FOOT
* WALKING&#x20;
* RUNNING&#x20;
* STILL&#x20;
* UNKNOWN&#x20;
* TILTING

## Adding a local Device Activity tile

* menu -> Edit -> Add Tile
* select Device Activity

<div align="left"><figure><img src="../.gitbook/assets/image (238).png" alt="" width="188"><figcaption></figcaption></figure></div>

The first time you add this tile it will show "no permission". Click on this tile to show the physical activity permission prompt

<div align="left"><figure><img src="../.gitbook/assets/image (242).png" alt="" width="91"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../.gitbook/assets/image (243).png" alt="" width="188"><figcaption></figcaption></figure></div>

Once permission is granted, you will see your device's current activity state displayed in a tile

<div align="left"><figure><img src="../.gitbook/assets/image (241).png" alt="" width="91"><figcaption></figcaption></figure></div>

## Sending device activity to Hubitat Hub

If you want your current device activity state to be sent to your Hub,&#x20;

* Add the [HD+ Tile](hd+-tile.md) to your Hubitat and select "Device Activity" for the type
* Make sure to add this new tile to MakerAPI so HD+ can see it
* long-press on the new tile in HD+ to open the Edit menu
* check "sync with device" checkbox
