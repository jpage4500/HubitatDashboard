---
description: How to install and use the HD+ Companion app+driver
---

# HD+ Companion App/Driver

## Description

HD+ Companion App/Driver is a Hubitat Hub app and driver which works with HD+ and allows you to send 'push' notifications from the hub to your phone. With it, you can:

* show system notifications on your phone
* play messages via Text To Speech (TTS)
* run Tasker tasks

![](<../.gitbook/assets/image (249).png>)

## Alternatives

You can already get push notifications to your phone today using the native [Hubitat app](https://docs2.hubitat.com/en/mobile-app). It will create a new Hubitat device for you and because Hubitat has a cloud server it's already configured to push messages from your Hub to your phone without any additional work needed.

## Google pre-requisite setup

* This is the complicated part. It's required so your Hub can send push messages to your device via Firebase Cloud Messaging (Hub -> Google Servers -> phone)
* Since everyone owns their own 'server' (aka: Hubitat Hub), I can't just create an account myself to do this and use the same API Key on everyone's Hub.
* In effect, you need to obtain 2 API keys.. 1 for the Hub to talk securely to Google and another for the phone to receive push messages from the Hub

1. Navigate to [Firebase Console](https://console.firebase.google.com/) (you'll need to login with a Google account)
2. Click on Create a Project
3. Enter project name. The name isn't important but I used "HD Companion"
4. You'll be asked to enable Google Analytics.. I disabled this (shouldn't matter either way)
5. When done, you'll be at a screen that says "Get started by adding Firebase to your app". Click on the little Android icon

<div><figure><img src="../.gitbook/assets/1 - create project.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/2 - name.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/3 - analytics.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/4 - android.png" alt=""><figcaption></figcaption></figure></div>

6. Fill in the following details about the app
   1. "Android package name" -> "com.jpage4500.hubitat"
   2. "App Nickname" -> "HD+" (optional)
   3. "Debug signing certificate SHA-1 (optional)" -> leave this empty
7. Click Register app
8. Click Download `google-services.json`. You'll need this file later!

<div><figure><img src="../.gitbook/assets/5 - android app name.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/6 - google-services.png" alt=""><figcaption></figcaption></figure></div>

9. Click Next -> Next -> Continue to Console
10. Click on your new project icon, HD+ and click on the little gear/settings icon
11. You should be on the Project Settings screen. Click on Cloud Messaging and then Manage Service Accounts link
12. This will open a new tab with your project. Click on the little hamburger icon in top-left corner -> API's and Services -> OAuth consent screen
13. Select `External` -> `Create` button
14. Enter app name (HD Companion), support email address (your email address) and developer contact (your email address)
15. Scroll down and click `Save and Continue` button

<div><figure><img src="../.gitbook/assets/7 - continue to console.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/8 - hd plus (b).png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/9 - project settings.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/10 - cloud - oauth consent.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/11 - oauth1.png" alt=""><figcaption></figcaption></figure></div>

<div><figure><img src="../.gitbook/assets/11 - oauth2.png" alt=""><figcaption></figcaption></figure> <figure><img src="../.gitbook/assets/11 - oauth3 test users.png" alt=""><figcaption></figcaption></figure></div>

16. Hit `Next` button on the Scopes tab
17. On the Test users screen, add your email address. `Save and Continue` again
18. Find and select the `Credentials` link on the left
19. Click on "`+ CREATE CREDENTIALS`" -> OAuth client ID
20. Select `Application type` == `Web application`
21. Enter a name for the client, e.g. `Hubitat Companion`
22. Under `Authorized redirect URIs`, click `+ ADD URI` and enter: `https://cloud.hubitat.com/oauth/stateredirect`
23. Click `CREATE`
24. You will see the new entry under `OAuth 2.0 Client IDs` -- on the far-right, click the download icon and then `DOWNLOAD JSON` button to download OAuth credentials. This file should start with "`client_secret_*.json`" You'll need this file later!

<figure><img src="../.gitbook/assets/12 - oauth download.png" alt=""><figcaption></figcaption></figure>

25. Before you're done - click on the OAuth consent screen item in left menu and hit PUBLISH APP button. I believe this is necessary to keep the OAuth token active ongoing

<figure><img src="../.gitbook/assets/image (248).png" alt=""><figcaption></figcaption></figure>

## Install HD+ Companion App/Driver

* Install [Hubitat Package Manager](https://hubitatpackagemanager.hubitatcommunity.com/) (HPM) if not already installed
* Use HPM -> Install -> Search for keyword: "HD+ Companion" to install the app and driver
  * NOTE: this replaces an older driver called "HD+ Device". It should update fine but if not please uninstall HD+ Device driver first

## Configure HD+ Companion App

You're going to need to open both the .json files you downloaded earlier. Open them in a text editor.

* Add a new App to the Hub (Add User App -> HD+ Companion)
* Fill in the 5 required fields. The first 2 are needed for the server app and the last 3 are needed for HD+
* From the `client_secret_*.json` file:
  * **Client ID**
    * `"client_id": "123456789-abcd.apps.googleusercontent.com",`
  * **Client Secret**
    * `"client_secret": "VALUE",`
* From the `google_services.json` file
  * **Project ID**
    * `"project_id": "hd-companion-12345",`
  * **API Key**
    * `"current_key": "VALUE"`
  * **App ID**
    * `"mobilesdk_app_id": "1:333482833076:android:XXXX6db1a53e1",`
* After filling in these fields you should see a button show up "Authorize App". Click this and follow the instructions on Google to login and allow access to your Hub to send push messages. When done you should get a link to return back to the Hubitat app

<figure><img src="../.gitbook/assets/image (250).png" alt=""><figcaption></figcaption></figure>

## Add newly created HD+ Device to MakerAPI

* The HD Companion app will create a new device called "HD+ Device"
* Open MakerAPI and add this new device so HD+ can access it

## Configure HD+

* In HD+ find this new device, long-press and hit Edit
* Open "Push Notifications"
* Enable "Link Device" to allow this Hubitat device to send push notifications to this phone\
  ![](<../.gitbook/assets/image (49).png>)<img src="../.gitbook/assets/image (50).png" alt="" data-size="original">

## Verify

* Once you link HD+ and the Hubitat device, HD+ will try to get a 'client key' and set it on the device. You can verify this by viewing the device on the hub and look for `clientKey` to be set

<figure><img src="../.gitbook/assets/image (251).png" alt=""><figcaption></figcaption></figure>

## Button Commands

The HD+ Device driver supports PushableButton, which means you can use it as a virtual button in your Hubitat Hub.

When pushed, an event is sent to the device which you can use to run a Tasker task (today, other actions will be added in the future)

Use the "Button Commands" setting (see above) to set an action for each button press. You will need Tasker installed to use this\
![](<../.gitbook/assets/image (51).png>)

## What Next?

* Use this new Hubitat device driver for sending either text or TTS notifications
* The guide below shows how to do both text or TTS notifications

{% embed url="https://docs2.hubitat.com/apps/notifications" %}

## And More...

* This device driver also supports presence and can be used with the [Presence Tracking (Geofence)](../features/presence-tracking-geofence.md) feature

## Notes

* This device driver / feature currently only works with Google supported devices and not with Amazon Fire devices. This is because Amazon doesn't support Firebase Cloud Messaging (FCM). Once this is all working well I'll try to also support [Amazon](https://developer.amazon.com/docs/adm/overview.html)'s version of pushing messaging as well

## Troubleshooting

If you're having any trouble getting notifications or TTS to work check these things:

1. you're running the latest beta version of HD+ (1.0.2196 or greater)
2. make sure the "HD+ Device" driver is added to MakerAPI
3. find this device in HD+ and check "Support Notifications"
4. look at the HD+ Device driver page and ensure both client key and server key are set (HD+ will do this for you). If either one isn't set - you might need to email me device logs along with what device you're using.

<figure><img src="../.gitbook/assets/image (209).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (210).png" alt=""><figcaption><p>Seen in HD+ Device Hubitat webpage</p></figcaption></figure>
