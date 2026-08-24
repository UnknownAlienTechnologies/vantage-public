---
layout: default
title: Vantage — Support
---

Vantage turns a spare iPhone into a standards-compliant IP camera: it serves an RTSP video stream
and an ONVIF Profile S service, so a network video recorder can adopt it like any other camera.

Contact: **joshualipovic@gmail.com**

---

## Getting started

1. Open the app and set a password when it asks. This protects the video stream, the snapshot and
   the camera's settings — a recorder must supply it.
2. Note the address shown at the top of the screen, e.g. `192.168.1.50`.
3. In your recorder, add a camera **by IP address**. Use username `admin` and the password you set.
4. Give the phone a fixed address (a DHCP reservation) on your router. Recorders identify cameras by
   address, so a changing one looks like a camera that has disappeared.

The phone must stay **plugged in with the app in the foreground**. iOS does not allow camera access
from the background, so this is a limit of the platform rather than a choice — the app keeps the
screen awake, and a "dim screen" control lets the display go dark while streaming continues.

---

## Frequently asked

**My recorder cannot find the camera.**
Check that the phone and the recorder are on the same network and the same subnet — many routers put
a guest network on a separate one. Confirm the app is in the foreground and showing a live picture.
Then open `http://<phone-ip>:8081` in a browser on the same network: if the control page loads, the
phone is reachable and the problem is in the recorder's settings.

**It asks for a password and mine is refused.**
The username is `admin` unless you changed it in Settings. The password is the one set in the app,
not your Apple ID or your recorder's password. If you have forgotten it, set a new one in
Settings → ONVIF credentials, then remove and re-add the camera in your recorder — recorders cache
credentials from when the camera was adopted.

**The picture looks stretched or squashed in my recorder.**
Remove the camera from the recorder and add it again. Recorders record the picture's dimensions when
they adopt a camera, and if the resolution has changed since then the old dimensions are used to lay
out the image. Re-adopting makes it read the current ones.

**Which resolution should I use?**
1080p at 30 fps for most purposes. 4K is available with Pro, but it makes the phone considerably
hotter, uses far more network bandwidth and disk space on your recorder, and adds little for a fixed
camera view. The app defaults to a middle setting derived from what your phone's lens actually
supports.

**The phone gets hot.**
Expected for continuous video encoding, and the app reduces bitrate automatically when the phone
reports thermal pressure. To reduce it: lower the resolution or frame rate, use the dim-screen
control, and avoid direct sunlight. A case that traps heat makes it worse. If you have enabled
"Ignore temperature" in Settings, the app holds your chosen quality instead of protecting the phone.

**Can I use it over the internet, away from home?**
Not directly, and deliberately. The app serves only your local network — there is no cloud, no
relay, no account. If you need remote access, use your recorder's own remote features or a VPN into
your home network. Forwarding these ports from the internet is strongly discouraged: the connection
is not encrypted.

**Two-way talk does not work in my browser.**
Browsers only allow microphone access on a secure page, and the app serves plain HTTP because it
cannot obtain a certificate for a device on a home network. Talk works when the control page is
opened **on the camera phone itself** at `http://127.0.0.1:8081`, because browsers treat that as
trustworthy. There is no way around this from the app's side.

**Recording on the phone stopped.**
Recording needs the app in the foreground with the screen on. Check the free space on the phone: the
app always leaves 2 GB free and deletes the oldest clips to stay within that and within the
retention window you chose. In the free version the retention is capped at one hour.

**I bought Pro and it is not unlocked.**
Tap **Restore purchase** on the Pro screen. Purchases are tied to your Apple ID, so make sure the
phone is signed in to the same account you bought with.

---

## Known limitations

- **Foreground only.** iOS revokes camera access from a backgrounded app. The camera stops if you
  switch apps or lock the phone.
- **One phone, one camera.** Recorders identify cameras by IP address and ignore the port, so a
  single phone cannot present as two cameras.
- **No encryption.** Traffic on your network is not encrypted. The password prevents casual access;
  it does not protect against someone who can capture traffic on your own network.
- **One stream quality.** The app advertises a single stream. Recorders that expect a separate
  low-resolution substream will say so; the stream itself still works.
- **No two-way talk from a recorder.** UniFi Protect does not support two-way audio or live audio
  playback for third-party ONVIF cameras. Talk works from the app's own web page only.

---

## Compatibility

**Verified on real hardware:** UniFi Protect — adopted, streaming and recording. Also verified as
clients: VLC, ffmpeg/ffplay, and standard ONVIF tools.

Anything that accepts a third-party ONVIF or RTSP camera should work — Home Assistant, Frigate, Blue
Iris, Synology Surveillance Station, Scrypted and similar. These implement the same standards, but
they have not each been tested end to end, so they are described as expected rather than verified.

**Requires** iOS 17 or later, and a recorder or viewer that speaks RTSP or ONVIF.

---

## Reporting a problem

Email **joshualipovic@gmail.com** with:

- what your recorder is, and its version
- what the app's screen shows (a photo is ideal)
- the exact error your recorder reports

If it is a streaming problem, the app's **Diagnostics** screen shows frame counters for each stage of
the pipeline — captured, encoded, delivered. The first stage that has stopped is where the problem
is, and quoting those numbers makes it far quicker to identify.

---

[Privacy policy](./privacy)
