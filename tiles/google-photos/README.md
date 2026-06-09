---
description: Add Google Photos Cloud album integration to your dashboard
---

# Google Photos

## Description

Add a Google Photos Cloud album to the dashboard to display a slide-show of your pictures

<div align="left"><figure><img src="../../.gitbook/assets/image (33).png" alt="" width="375"><figcaption></figcaption></figure></div>

## Install Hubitat App/Driver

* Install [HPM](https://hubitatpackagemanager.hubitatcommunity.com/) (Hubitat Package Manager) to your Hubitat
* Open HPM -> Install -> Search by keywords -> search for **Google Photos Cloud**

## Install **Google Photos Cloud**

* In Hubitat Apps section, click on Install User App -> **Google Photos Cloud**
* Enter **Google Client ID / Secret**
  * Refer to [get-google-credentials.md](get-google-credentials.md "mention") to get the Client ID and Client Secret (free)
* Click **Authorize** to authorize this app with Google Photos

<div align="left"><figure><img src="../../.gitbook/assets/image (1).png" alt="" width="375"><figcaption></figcaption></figure></div>

* Enter an album name and click on the little save icon next to it
* Click **Create Album** button which will create a new Google Photos album and a child device on Hubitat with the same name

<div align="left"><figure><img src="../../.gitbook/assets/image (7).png" alt="" width="265"><figcaption></figcaption></figure></div>

* Select any other options - such as how frequently the next image should display
* **Don't forget to add this new child device to MakerAPI so HD+ can see it**

## Usage

* HD+ will automatically handle and display these devices so there's nothing you need to do
* Depending on the refresh interval you chose, the image will change automatically

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

<div align="left"><figure><img src="../../.gitbook/assets/image (27).png" alt="" width="188"><figcaption></figcaption></figure></div>

* see [background.md](../../look-and-feel/background.md "mention") for more details
