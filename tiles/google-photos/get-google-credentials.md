---
description: Create a free Google Client ID and Client Secret for the Google Photos app
---

# Get Google Credentials

The Google Photos app needs a **Client ID** and **Client Secret** so Google can let it access the photos you pick. You create these for free in the Google Cloud Console — about 10 minutes, and you only do it once.

## 1. Create a project

* Go to [console.cloud.google.com](https://console.cloud.google.com)
* Click the project dropdown in the top bar → **New Project**
* Name it (e.g. `Hubitat`) → **Create** → select the new project

## 2. Enable both Photos APIs

Use the search bar at the top to find and **Enable** each of these:

* **Photos Library API** — lets the app create an album and upload your picked photos
* **Photos Picker API** — lets you pick the photos in the first place

> Both are required. Older guides only mention the Photos Library API — if you skip the Picker API the photo picker won't open.

## 3. Configure the consent screen

* Left menu → **APIs & Services** → **OAuth consent screen**
* User type: **External** → **Create**
* Fill in an app name and your email, then **Save and Continue** through the pages
* On **Test users**, click **Add Users** and add your own Google account email → **Save**

> Leave the app in **Testing** mode — that's fine for personal use and needs no Google verification. But you must add yourself as a test user, or Google will block sign-in.

## 4. Create the OAuth client

* Left menu → **Credentials** → **Create Credentials** → **OAuth client ID**
* Application type: **Web application**
* Name: `Hubitat`
* Under **Authorized redirect URIs** → **Add URI** and enter exactly:

```
https://cloud.hubitat.com/oauth/stateredirect
```

* Click **Create**

## 5. Copy into the app

* A dialog appears showing your **Client ID** and **Client Secret**
* Paste each into the matching field in the Google Photos app
* **Save** → **Authorize App** → sign in with the same Google account you added as a test user

> The redirect URI must match exactly (no trailing slash). You can re-open the client under **Credentials** any time to copy the ID and secret again.
