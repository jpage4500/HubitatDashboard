---
description: Add a video stream tile to your dashboard
---

# Video Tile

To start, put the app into Edit mode -> Add Device -> Video Tile

<figure><img src="../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

Enter the URL of the video stream you want to view. The app supports a few types/formats for video streaming:

* [MJPEG](https://en.wikipedia.org/wiki/Motion_JPEG)
  *   Examples:

      <pre><code><strong>http://pendelcam.kip.uni-heidelberg.de/mjpg/video.mjpg
      </strong></code></pre>
* [RTSP](https://en.wikipedia.org/wiki/Real_Time_Streaming_Protocol) - the URL will start with "**rtsp**://" or "**rtsps**://" and can have an optional username and password.
  * _NOTE: I've found several links to test rtsp streams but they're not working.. if anyone has some good examples let me know_
* Youtube - a link to a Youtube video or livestream
  *   Examples:

      ```
      https://www.youtube.com/live/x8OlhNaD5as?si=cuBm0is2ww3ugJ0J
      ```

<div align="left"><figure><img src="../.gitbook/assets/image (43).png" alt="" width="188"><figcaption></figcaption></figure></div>

<div align="left"><figure><img src="../.gitbook/assets/image (217).png" alt="" width="375"><figcaption><p>Reolink RLC-410W</p></figcaption></figure></div>

## Video Drivers

The app will try to pick a video driver to match the video source. But, in some cases you might want to try another driver if the video doesn't play. HD+ embeds 4 open source video libraries:

* [ExoPlayer](https://exoplayer.dev/) - this is a large open source driver which supports MANY formats
* [MJPEG](https://github.com/niqdev/ipcam-view) - this driver is specific to MJPEG video
* [RTSP](https://github.com/alexeyvasilyev/rtsp-client-android) - this driver is specific to RTSP video; I've personally found this driver faster than ExoPlayer if you have a camera that supports RTSP video
* [Youtube](https://github.com/PierfrancescoSoffritti/android-youtube-player) - this driver will play back Youtube videos

<div align="left"><figure><img src="../.gitbook/assets/image (44).png" alt="" width="375"><figcaption></figcaption></figure></div>

## Change Video Driver

* long-press on a video tile
* select Video Driver

<div align="left"><figure><img src="../.gitbook/assets/image (45).png" alt="" width="188"><figcaption></figcaption></figure></div>

## Video Camera URL

If you have a video camera, check that it supports rtsp protocol. Many of the cloud-connected cameras today don't support this but there's several lists of those that do.

* [https://www.avertx.com/faqs/list-of-thirdparty-camera-rtsp-urls/](https://www.avertx.com/faqs/list-of-thirdparty-camera-rtsp-urls/)
* [https://help.nsoft.vision/hc/en-us/articles/4411595651345-List-of-RTSP-URLs-of-security-camera-manufacturers](https://help.nsoft.vision/hc/en-us/articles/4411595651345-List-of-RTSP-URLs-of-security-camera-manufacturers)
* [https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv](https://github.com/CamioCam/rtsp/blob/master/cameras/paths.csv)

## Video Support

I've only been able to test streaming video on a few different cameras.&#x20;

If you're unable to get an RTSP video working, you can try isolating the issue by using the following demo app. This apk is the latest demo app from the [rtsp library](https://github.com/alexeyvasilyev/rtsp-client-android) I'm using in HD+

* [https://jpage4500.s3.amazonaws.com/hubitat-dashboard/rtsp-client-android.apk](https://jpage4500.s3.amazonaws.com/hubitat-dashboard/rtsp-client-android.apk)

If your camera stream works in this demo app but not HD+ please let me know and I'll investigate

