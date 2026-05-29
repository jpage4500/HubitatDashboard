---
description: How to setup Life360+ Hubitat App
---

# Life360+

## Description

Life360+ is a Hubitat app which will create Hubitat devices for every Life360 member you want to view location for. More details are available on the Hubitat support page [here](https://community.hubitat.com/t/release-life360/118544)

## Installation

Install Life360+ via Hubitat Package Manager (HPM)

## Configuration

Because of changes to Life360's login flow, you'll need to get your own access token. This is the complicated part but I'll try to describe how I got mine step by step.

* Open a browser to [https://life360.com/login](https://life360.com/login) on your computer (using Chrome/Brave as an example)
*   Open the developer tools sidebar

    <div align="left"><figure><img src="../../../.gitbook/assets/image (252).png" alt="" width="375"><figcaption></figcaption></figure></div>
* Select the Network tab in developer tools sidebar
* Login to Life360 using your phone number (NOTE: this has only been tested using phone numbers, not email/password which Life360 is phasing out)
* If you can't login, try disabling your ad-blockers. I'm using Brave and I had to disable both the internal blockers as well as uBlock Origin add-on for the login to work
*   Once logged in, click on the little search icon in developer tools sidebar and search for "access\_token". You should see a result similar to below:

    <figure><img src="../../../.gitbook/assets/image (253).png" alt=""><figcaption></figcaption></figure>

    * IF you can't find it, look for this screen
    *

        <figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
* **Copy the value of access\_token**. This is what you're going to enter in the Life360+ app
* Add the Life360+ app to Hubitat and open it
*   Enter the access token and hit the save icon

    <figure><img src="../../../.gitbook/assets/image (254).png" alt=""><figcaption></figcaption></figure>
* You should see more options displayed once the access token is set
* Hit Fetch Circles and select your primary circle
* Hit Fetch Places and select the place which correpsonds to your home (used to set the child devices as home or away)
* Hit Fetch Members and select all members you want to track
* When you hit DONE, child devices will be created matching the members you created



NOTE: The credit for this belongs [here](https://github.com/pnbruckner/ha-life360) -- I'm just simplifying the steps
