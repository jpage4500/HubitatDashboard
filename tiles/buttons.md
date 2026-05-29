---
description: Hubitat Button Devices
---

# Buttons

Hubitat Dashboard supports multiple buttons on a single device / tile and offers several ways to configure these.

By default, a single button device will show up like this:

<img src="../.gitbook/assets/image (153).png" alt="" data-size="original">

A device that has multiple buttons (4) would show up like this:

![](<../.gitbook/assets/image (124).png>)

### Click Actions

*   By default, clicking on a button will bring up a larger dialog. From there, you can send different commands to the Hub:

    1\) click will send 'press' command\
    2\) double-tap will send 'doubleTap' command\
    3\) press and hold will send the 'hold' command\
    ![](<../.gitbook/assets/image (204).png>)
* You can change the click behavior by setting the device's '[click action](../features/click-action.md)' to be 'toggle' instead of 'prompt'. Then, clicking on the button on the main dashboard will send the 'press' command directly.
* long-pressing on the button tile will bring up the device details dialog. From here, you can click, double-tap or press and hold on the button to send these commands to the hub.\
  ![](<../.gitbook/assets/image (192).png>)

### Configure Buttons

If you have more than 1 physical button on your 'button' device, you can configure each of them individually to show text or an image.

* long-press on a button to open up the details screen and hit "Edit" to view the edit screen
* click on Manage Buttons to view all of the buttons for that device

![](<../.gitbook/assets/image (115).png>)![](<../.gitbook/assets/image (202).png>)

* To show an image instead of a label, click on the little picture icon next to the button you want to change
* To change the button label, click on the large button with the current label (ie: "1")

![](<../.gitbook/assets/image (158).png>)

### Additional Notes

* Only 4 buttons will display on a single 1x1 tile. But, you can change the tile size to make up to 5 buttons visible on a tile if you change the size to be > 1 row tall

![](<../.gitbook/assets/image (96).png>)![](<../.gitbook/assets/image (143).png>)



* see this Youtube video for an example: [https://www.youtube.com/watch?v=iRlq5586LKY](https://www.youtube.com/watch?v=iRlq5586LKY)
