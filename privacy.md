---
layout: default
title: Vantage — Privacy Policy
---

Last updated: 24 August 2026

## Summary

Vantage collects nothing. There is no analytics, no tracking, no advertising, and
no account. Nothing is sent to the developer or to any third party.

## What the app accesses, and why

**Camera.** Used to capture the video the app streams. Video is encoded on the device
and sent only to clients that connect to it on your own network — typically a network
video recorder such as UniFi Protect, or a browser you open yourself.

**Microphone.** Optional and off by default. When enabled, audio is included in the
stream alongside video, sent to the same local clients.

**Local network.** The app runs RTSP, ONVIF, and web servers on the device so
recorders and browsers on your network can reach it. These run only while the app is
open in the foreground.

## What is stored on the device

- The username, password, and API token you set, kept in the iOS keychain.
- A randomly generated identifier used to give the camera a stable network identity
  across restarts, kept in the app's own preferences.
- Your camera settings.

All of this stays on the device. Deleting the app removes it.

## What leaves the device

Only the video and audio stream, and only over your own local network. The developer has
no access to it, and no server is involved in it.

The video stream, the snapshot and the camera's settings all require the password you set
in the app. Nothing on your network can view the camera without it.

The connection is not encrypted, though, because the app cannot obtain a certificate for a
device on a home network. So treat the network itself as part of the boundary: the password
stops casual access, not someone who can capture traffic on your own LAN.

## Children

The app is not directed at children and collects no personal information from anyone.

## Contact

Questions about this policy: <!-- Replace with your contact email before publishing. -->
