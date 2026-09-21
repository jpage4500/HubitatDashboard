# Privacy Policy — HD+

**Last updated: September 17, 2026**

HD+ ("the app") is made by Joe Page. This policy covers the Android, iOS, macOS, Windows and Linux
versions

The short version: **there is no account, no advertising, and no third-party analytics or tracking
SDK.** The app is a client for a hub you own, on your own network. Your dashboard and settings live
on your device and on that hub. The developer runs no server that your dashboard talks to.

---

## What stays on your device

Everything you configure: your hub's address, its Maker API access token, the cloud token if you set
one up, your dashboard layout, every tile's settings, theme, screensaver and kiosk options, camera
stream URLs, geofences, and any API key you entered yourself (Google Maps, Google Pollen). Hub Login
Security credentials are stored only if you leave "Remember Me" on.

These are kept in the platform's normal settings store — Android `SharedPreferences`, iOS
`UserDefaults` (in an app group, so the widgets can read the same values), and a folder under
`~/.hubitat-dashboard/` on desktop. None of it is uploaded anywhere
except where you ask for it (see **Support reports and crashes** below), and deleting the app removes
it.

Device state, images and video frames are also cached on the device so the dashboard draws
immediately instead of coming up blank. The app keeps a rolling local log file (it rotates at 2 MB)
that exists for support; nothing reads it unless you send it.

---

## What lives on your hub

A dashboard is stored on the hub as attributes on your devices, so the layout follows you to every
copy of the app and survives a reinstall. Config backups you save go to the hub or to a file you
pick. That is your hardware and your network — the developer has no access to any of it.

---

## Talking to the hub

- **Local.** By default every request goes straight to the hub's IP address on your LAN. Nothing
  leaves your network, and there is no intermediary.
- **Cloud.** If you set up a cloud token, the app can reach the hub through `cloud.hubitat.com` when
  you're away from home — that is Hubitat's own service, under
  [their privacy policy](https://hubitat.com/privacy). It's used only when you enable it, and in the
  default "Auto" mode only when the hub can't be reached locally.
- **Discovery.** Finding a hub sends a UPnP/SSDP search on the local network only.

---

## Location

Location is used for exactly one optional feature: **presence**. A geofence you draw around home
lets the app tell your hub you've arrived or left, so your own automations can run.

- It is **off until you add a geofence** (More Settings ▸ Presence Tracking), and permission is only
  requested then.
- It needs background location on Android and iOS, because the whole point is to notice an arrival
  while the app isn't open. Motion/activity data (driving → stopped) is used on the same feature to
  confirm an arrival that the OS geofence reported unreliably.
- **Your coordinates are never transmitted.** The only thing sent when a geofence trips is an
  arrived/departed command to a presence device on *your* hub — the same command a button press
  would send. The geofence itself is stored on your device.
- Decline location, or add no geofence, and everything else in the app works normally.

Weather, radar and pollen tiles do **not** use your device's location. They use the place you typed
or searched for when you added the tile.

---

## Cameras

Two unrelated things are called "camera" here:

**Your cameras.** Video tiles connect straight to the RTSP/HTTP URL you entered, on your network.
Frames are decoded on the device and never leave it. Screenshots and recordings are saved where you
would expect — the photo library on Android and iOS, a file you choose on desktop — and are uploaded
nowhere.

**The front camera, for Wake On Motion.** Part of the screensaver: the camera watches for movement so
the dashboard wakes as you walk up to it instead of waiting for a tap.

- It is **off by default**, and camera permission is only requested if you switch it on.
- The camera is open **only while the screensaver is actually on screen**, and closes the moment the
  screensaver does.
- No photo or video is recorded, saved, or sent anywhere. The app compares the overall brightness of
  one frame against the previous one and keeps nothing else — there is no image to leak, and nothing
  leaves your device.
- It's mobile only. The desktop app never touches a camera.

---

## Notifications

Timers and alarms you set in the app fire local notifications from the device itself. Nothing is sent
to a push server — there is no push server.

---

## Services the app contacts

Most tiles need nothing but your hub. The ones below reach out, and each service necessarily sees
your device's IP address and whatever the request carries, under its own privacy policy.

| Service | What it receives | When |
|---|---|---|
| Your hub, and your cameras | Everything the dashboard does | Always — on your local network |
| [cloud.hubitat.com](https://hubitat.com/privacy) | The same requests, with your cloud token | Only in cloud mode, or when the hub isn't reachable locally |
| [Iowa State University Mesonet](https://mesonet.agron.iastate.edu/) (NOAA HRRR) | The map area the tile is showing | While a radar tile is on screen, with the default source |
| [weather.com](https://weather.com/en-US/twc/privacy-policy) | The map area the tile is showing | Only if you pick it as the radar source |
| [Esri](https://www.esri.com/en-us/privacy/overview) / [OpenStreetMap](https://osmfoundation.org/wiki/Privacy_Policy) | The map area being drawn | Under a radar or map tile |
| [Google Static Maps](https://policies.google.com/privacy) | Coordinates, your API key | Location map tile, only with a key you added |
| [Google Pollen](https://policies.google.com/privacy) | Coordinates, your API key | Pollen tile, only with a key you added |
| [pollen.com](https://www.pollen.com/privacy) | A US ZIP code | Pollen tile, in the US |
| [Open-Meteo](https://open-meteo.com/en/terms) | The place name you type | Searching for a location when adding a tile |
| [Unsplash](https://unsplash.com/privacy) | A search term you type | Only while picking a background or image from Unsplash |
| [Iconify](https://iconify.design/privacy) | A search term you type | Only while searching for a tile icon |
| [Apple](https://www.apple.com/legal/privacy/), [Deezer](https://www.deezer.com/legal/personal-datas), [IMDb](https://www.imdb.com/privacy), [Bing](https://privacy.microsoft.com/privacystatement) | The name of what's playing, to find artwork | While a media tile is showing something with no artwork of its own |
| [OpenWeatherMap](https://openweather.co.uk/privacy-policy), [GitHub](https://docs.github.com/site-policy/privacy-policies/github-general-privacy-statement) | An icon file name | Weather tile icons |
| [icanhazdadjoke.com](https://icanhazdadjoke.com/) | Nothing but the request | A Text tile set to show a joke |
| [GitHub](https://docs.github.com/site-policy/privacy-policies/github-general-privacy-statement) | Nothing but the request | Update checks — **sideloaded Android and desktop only.** App Store and Play Store builds never do this |
| Calendar and web addresses you add | Whatever that address serves | While a calendar, web or shortcut tile you configured is in use |

The developer does not receive a copy of any of these requests. Links you tap in the app — the
Hubitat community, documentation, an app store page — open in your browser and leave the app behind.

---

## Support reports and crashes

This is the one place data reaches the developer, and it is the only one.

**When you send a support report** (About ▸ Support / Feedback), the app uploads the local log
file so a problem can be reproduced. Hub tokens are obscured before they're sent. 
The log holds what the app was doing: app version, OS version, device model,
battery level, memory, CPU count, device and tile names, and local addresses. No location, and no
video or camera frame.

**If the app crashes**, the same upload happens automatically on the next launch, and the app says so
with a "Reporting crash" message. That is the only upload you don't start yourself.

Uploads go to a private storage bucket the developer controls, and are used for nothing but fixing
the problem. They are deleted automatically after a short period of time

---

## What the app never does

- No advertising, ad network, or ad ID.
- No third-party analytics, attribution, or tracking SDK — there is no usage tracking of any kind.
- No account, sign-in, or email collection. The only login is to your own hub.
- No selling or sharing of data with anyone, for any purpose.
- No device location reported to anyone, and no coordinates sent to your hub.
- No photo or video from any camera — yours or the device's — is stored or transmitted, ever.

---

## Children

The app isn't directed at children, and it doesn't knowingly collect anything from them. It has no
account system and collects no personal information from anyone.

---

## Your choices, in one place

| To do this | Go here |
|---|---|
| Stop using location | More Settings ▸ Presence Tracking — delete your geofences, or revoke location permission in the OS |
| Stop the app using the front camera | More Settings ▸ Dashboard Mode ▸ Screensaver ▸ Wake On Motion — turn it off, or revoke camera permission in the OS |
| Keep everything on your LAN | Hub Details ▸ Cloud Mode — set it to Off, and don't add a cloud token |
| Stop contacting Unsplash | Pick a bundled image, a color or a gradient instead |
| Forget your hub credentials | Log out, or turn off "Remember Me" |
| Remove everything stored locally | Uninstall the app (desktop: delete `~/.hubitat-dashboard/`) |

---

## Contact

Questions, or a deletion request: **joe.page.software@gmail.com**, or send a report through the app
(About ▸ Support / Feedback).
