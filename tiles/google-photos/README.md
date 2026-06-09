---
description: Add Google Photos album integration to your dashboard
---

# Google Photos

## Description

Add a Google Photos album to the dashboard to display a slide-show of your pictures

<div align="left"><figure><img src="../../.gitbook/assets/image (33).png" alt="" width="375"><figcaption></figcaption></figure></div>

## Install

* See [this](https://community.hubitat.com/t/project-google-photos-integration-for-dashboard-image-slide-show/72686) page for details
  * Install using Hubitat Package Manager
  * In Apps, add user app -> Google Photos
  * Refer to [get-google-credentials.md](get-google-credentials.md "mention") to get the Client ID and Client Secret needed
* Make sure to add any new Google Photos devices you create to MakerAPI so HD+ has access to them

## Usage

* HD+ will automatically handle and display these devices so there's nothing you need to do
* Depending on the refresh interval you chose, the image will change automatically
* When clicking on a photo, it'll appear full-screen
  * Click on the right side of the screen to view the NEXT image
  * Click on the left side of the screen to view the PREVIOUS image

<div align="left"><figure><img src="../../.gitbook/assets/image (32).png" alt="" width="375"><figcaption></figcaption></figure></div>

## Use Google Photos as a Background

* Once you have a Google Photos device in HD+ you can use it for the dashboard background
* Open the menu -> Display Options -> Background

<div align="left"><figure><img src="../../.gitbook/assets/image (28).png" alt="" width="188"><figcaption></figcaption></figure></div>

* Choose Select Image
* Select Image Source in top-left corner of dialog
* Select Hubitat Device

<div align="left"><figure><img src="../../.gitbook/assets/image (29).png" alt="" width="188"><figcaption></figcaption></figure></div>

* Pick your Google Photos device from the list

<div align="left"><figure><img src="../../.gitbook/assets/image (30).png" alt="" width="188"><figcaption></figcaption></figure></div>

* Change the Transparency value to show more or less of the background

<div align="left"><figure><img src="../../.gitbook/assets/image (31).png" alt="" width="188"><figcaption></figcaption></figure></div>

* see [background.md](../../look-and-feel/background.md "mention") for more details

