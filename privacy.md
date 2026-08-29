---
layout: default
title: Vantage — Privacy Policy
---

# Privacy Policy — Vantage

Last updated: 29 August 2026

## Summary

Vantage collects nothing. There is no analytics, no tracking, no advertising, and
no account. Nothing is sent to the developer or to any third party.

## What the app accesses, and why

**Camera.** This is the whole point of the app: it captures the video. That video is encoded on
the device and then either recorded on the phone itself, or sent to whatever connects to it on
your own network — a recorder, or a browser you open yourself — or both, depending on which you
chose. It goes nowhere else.

**Microphone.** Optional and off by default. When enabled, audio is included in the
stream alongside video, sent to the same local clients.

**Local network.** The app runs RTSP, ONVIF, and web servers on the device so
recorders and browsers on your network can reach it. These run only while the app is
open in the foreground.

**Notifications.** Optional. If you allow them, the app posts a notification on this phone when the
camera has stopped doing its job — it has stopped filming, the picture has frozen, recording has
stopped, or the servers are not reachable — and withdraws it when the camera recovers. These are
local notifications, created and shown by the phone itself: nothing is sent to a server, there is no
push service involved, and no notification, and nothing about the state that caused it, leaves the
device. Permission is asked for at the end of setup rather than at launch, and refusing it changes
nothing else about how the app works.

## What is stored on the device

- The username and password you set, kept in the iOS keychain. The same password is the
  credential for the web page and the local API, so there is no second secret.
- A randomly generated identifier used to give the camera a stable network identity
  across restarts, kept in the app's own preferences.
- Your camera settings.
- A note that you were shown the safety information, and when. It records which version of that
  text you saw, so it is possible to say what you actually read rather than only that something
  appeared. It is a preference on this device, so it is included in your own device backup, and it
  is not sent anywhere.
- **Recorded clips, if you turn recording on.** Recording is off until you switch it on.
  When it is on, the app writes five-minute `.mp4` clips into its own Application Support
  folder, keeps them within a size budget (20 GB by default) and the retention window you
  choose, and deletes the oldest automatically to stay inside both. The clips are never
  uploaded anywhere: they stay on the phone until they age out, until you delete them, or
  until you export one yourself through the share sheet.

All of this stays on the device. Deleting the app removes your settings and any clips, because
both live in the app's own container. The username and password are in the iOS keychain, which
survives being uninstalled — "Reset everything" in Settings clears those.

## What leaves the device

Only the video and audio stream, and only over your own local network. The developer has
no access to it, and no server is involved in it.

The video stream, the snapshot, the recorded clips, the live audio feed and the camera's settings all
require the password you set in the app. Nothing on your network can see or hear the camera without
it. Audio — in the stream or as the live feed — exists only while you have switched the microphone
on, which is off by default.

Two health endpoints are the exception, deliberately: they report whether frames are still
flowing, what the phone's temperature is, and what formats the lens offers, and they answer
without a password because they are what you check when the picture has frozen — needing a
credential to diagnose a stall makes them useless at the moment they matter. Neither carries
video, audio, or your credentials.

The connection is not encrypted, though. A camera on a home network has no public name a
certificate authority will vouch for, so the app would have to present a certificate your
browser does not recognise — which every device would warn about. Rather than train people to
click through security warnings, the app serves plain HTTP and says so here. Treat the network
itself as part of the boundary: the password stops casual access, not someone who can capture
traffic on your own LAN.

## Children

The app is not directed at children and collects no personal information from anyone.

## Contact

Questions about this policy, or about anything the app does with your data:
**[joshualipovic@gmail.com](mailto:joshualipovic@gmail.com)**

See also the [support page](https://unknownalientechnologies.github.io/vantage-public/).
