---
description: Privacy Policy and App Permissions
---

# Privacy Policy

**Last updated:** 2026-05-28

### Summary <a href="#toc_1" id="toc_1"></a>

Hubitat Dashboard does not collect, transmit, or share any personal user data with the developer or any third party. All app data — settings, dashboard layout, device info from your Hubitat hub, and any data accessed via the permissions below — is stored **only on your device** and is only sent to services you explicitly configure (your Hubitat hub, or optional third‑party image/icon services you choose to enable).

### Data we collect <a href="#toc_2" id="toc_2"></a>

**None.** The developer does not operate any server that collects user data from this app. The app communicates with:

* Your Hubitat hub (locally over your Wi‑Fi network, or via `cloud.hubitat.com` if you enable cloud mode). Hubitat's own privacy policy governs that connection.
* Optional third‑party image / icon search services (Google Maps, Iconfinder, Unsplash, Finnhub) — only when you actively use a feature that requires them. Their privacy policies apply to those requests.
* Firebase Crashlytics — receives **anonymous** crash reports (stack traces, device model, OS version) if a crash occurs. No personally identifiable information is included.

### Data retention <a href="#toc_3" id="toc_3"></a>

Because no user data is collected by the developer, there is nothing retained on any server operated by the developer.

App data stored **on your device** (settings, dashboard configuration, cached device state) is retained for as long as the app is installed. It is not backed up to or synced with any developer‑operated service.

### Data deletion <a href="#toc_4" id="toc_4"></a>

You can delete all app data at any time by either:

1. **Uninstalling the app** — this removes all locally stored data, settings, and cache.
2. **Clearing app data** from your device — Android Settings → Apps → Hubitat Dashboard → Storage → "Clear data" / "Clear storage". This wipes all dashboard configuration and cached data without uninstalling.

Because the developer does not collect or store user data, there is no separate deletion request process needed. If you have questions, contact: joe.page.software@gmail.com.

### Permissions requested <a href="#toc_5" id="toc_5"></a>

The following permissions are requested by the app. None of these transmit data to the developer.

* **LOCATION** (optional)
  * Necessary for 'auto' cloud mode — the app switches between your local Wi‑Fi and `cloud.hubitat.com` for remote access by reading the connected Wi‑Fi SSID and comparing it to a saved SSID.
  * Required for the optional presence/geofence feature, which notifies **your** Hubitat hub of your present/not‑present state. Location data is **not** sent to the developer.
  * The presence feature also requests `REQUEST_IGNORE_BATTERY_OPTIMIZATIONS` and `ACTIVITY_RECOGNITION` to improve tracking accuracy.
  * [Cloud Mode](https://joe-page-software.gitbook.io/hubitat-dashboard/features/cloud-mode) · [Presence tracking](https://joe-page-software.gitbook.io/hubitat-dashboard/features/presence-tracking-geofence)
* **CAMERA** (optional)
  * Used in screensaver mode to detect motion via the front‑facing camera and wake the screen. Video is processed on‑device in real time and is **not** recorded, stored, or transmitted.
  * [Always On](https://joe-page-software.gitbook.io/hubitat-dashboard/features/keep-screen-on)
* **QUERY**_**ALL**_**PACKAGES** (optional, sideload build only)
  * Used to list installed apps so you can create an app‑launcher tile. The list of installed apps is **not** sent anywhere.
  * [Shortcuts](https://joe-page-software.gitbook.io/hubitat-dashboard/tiles/shortcut)
* **NFC** (optional)
  * Used to read NFC tags and trigger an in‑app action. Tag data is **not** sent to the developer.
  * [NFC](https://joe-page-software.gitbook.io/hubitat-dashboard/features/nfc-tags)

### Children's privacy <a href="#toc_6" id="toc_6"></a>

This app is not directed at children under 13 and does not knowingly collect any data from them.

### Changes to this policy <a href="#toc_7" id="toc_7"></a>

Updates to this policy will be posted to this page with a new "Last updated" date.

### Contact <a href="#toc_8" id="toc_8"></a>

Questions about this policy: **joe.page.software@gmail.com**
