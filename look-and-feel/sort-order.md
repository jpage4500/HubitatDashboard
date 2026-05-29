---
description: How tiles are ordered
---

# Sort Order

There's several ways you can order devices & tiles on the dashboard

* **Device Type**
  * Prioritizes some device types over others. For example, security devices like Locks, Garage doors, Doors are displayed ahead of switches like lights.
  * Devices with the same device type (ie: Lock) are sorted by Name (A-Z)
  * This is the default sort order
* **Name (A-Z)**
  * Devices are sorted by Name (A-Z)
* **Last Updated**
  * Device are sorted by most recently updated devices first
  * NOTE: MakerAPI doesn't return the device updated time consistently so this option isn't recommended at this time. I have a support [request](https://community.hubitat.com/t/maker-api-what-does-the-date-field-represent/134717) open for this
* **Room (A-Z)**
  * Devices are sorted by Room. Note this is an optional field (see [this](https://docs2.hubitat.com/user-interface/rooms) page)
* **Custom**
  * Once you manually move a tile, the sort order will be locked and new devices will get added to the bottom of the list.
  * See [Drag and Drop](sort-order.md#drag-and-drop) tiles section

<div align="left"><figure><img src="../.gitbook/assets/image (24).png" alt="" width="188"><figcaption></figcaption></figure></div>

## Drag and Drop

Manually arrange tiles in any order you'd like.

* Put HD+ in Edit Mode (menu -> Edit Mode)
* Press and hold any tile for a few seconds
* While holding the tile, drag it to another place on the dashboard
* You can move tiles into a folder by dropping the tile on an existing folder
  * If you don't want to move the tile into the folder, just wait another second and the folder will move

<div align="left"><figure><img src="../.gitbook/assets/image (25).png" alt="" width="188"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../.gitbook/assets/image (26).png" alt="" width="188"><figcaption></figcaption></figure></div>
