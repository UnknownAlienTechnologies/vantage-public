---
layout: default
title: Vantage — Support
---

# Vantage — Support

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
Then open the control page in a browser on the same network — tap the address at the top of the app,
then scan the QR code or copy the link, which already carries your password. If the page
loads and shows the live picture, the phone is reachable and the problem is in the recorder's
settings.

**It asks for a password and mine is refused.**
The username is `admin` unless you changed it in Settings. The password is the one set in the app,
not your Apple ID or your recorder's password. If you have forgotten it, set a new one in
Settings → ONVIF credentials, then remove and re-add the camera in your recorder — recorders cache
credentials from when the camera was adopted.

**The picture looks stretched or squashed in my recorder.**
Remove the camera from the recorder and add it again. Recorders record the picture's dimensions when
they adopt a camera, and if the resolution has changed since then the old dimensions are used to lay
out the image. Re-adopting makes it read the current ones.

**How do I rotate the picture, or flip it?**
On the phone: tap **View** in the row of controls under the preview. It has rotation — automatic,
which follows the phone, or held at 90°, 180° or 270° for a mount that is not the way up the phone
thinks it is — a **Mirror** switch, and exposure. Held rotation is the one to use for a wall
bracket: automatic rotation follows the phone, and a phone screwed to a wall does not move. The same
controls are on the web control page, and either changes the picture your recorder receives. Some
lenses cannot mirror; the switch says so rather than doing nothing.

Recorders read the picture's dimensions once, when they adopt the camera, so a rotation that swaps
width and height may need the camera removed and re-added before the recorder lays it out correctly.

**Why did my clips disappear?**
They are deleted on a schedule, and the app never fills the phone. Three limits apply at once, and
whichever bites first wins: the retention window you chose in Settings → Recordings (in the free
version this is capped at one hour, whatever the setting says), the size budget (20 GB by default),
and a 2 GB floor of free space that overrides both — iOS terminates apps that fill the disk, and a
camera that has been killed records nothing at all. The oldest clip goes first. The Recordings
screen says in words how far back the clips on disk actually reach and what will be deleted, which
is worth reading before a search rather than after: a clip removed overnight leaves nothing behind
to explain itself.

Recording also needs the app in the foreground with the screen on, so a night when the phone was
locked or another app was in front has no clips at all.

**Will it tell me if it stops?**
Yes, on that phone. If the camera stops filming, the picture freezes and restarting has not helped,
recording stops for good, or the servers stop listening, the phone posts a notification once the
condition has lasted a minute — with a sound, and a timestamp you can read afterwards, which is the
difference between "it stopped some time in the last three days" and "it stopped at 02:14". It is
withdrawn again when the camera recovers. The app asks for notification permission at the end of
setup, which is the moment you are about to walk away from the phone; if you refused, Settings →
Notifications → Vantage is where to change it.

Be clear about the limit: these are local notifications on the camera phone itself. There is no
cloud service here, so nothing can be sent to another device, and a phone that has crashed, been
killed by iOS, run out of battery or rebooted posts nothing at all — the app has to be running to
notice. **Do not treat it as an alerting service**, and do not rely on it for anything that matters.

**Can someone listen to the room?**
Anyone on your network holding the password can, while the microphone is on. As well as the audio in
the RTSP stream, the camera serves a plain live audio feed at `/api/listen` — up to four listeners at
once — which is how a phone or a script can hear the room without opening the video. The control page
says in words whenever anybody is listening. The microphone is off by default and is a Pro feature,
so on a camera with the microphone off there is nothing to hear at all. If that is not what you
want, leave the microphone off — and remember that recording or transmitting sound is separately
restricted by law in many places, whatever your camera can do.

**Where are the sensitivity sliders, and the safety information?**
Settings → **Diagnostics** holds the Auto light tuning (sensitivity, darkness, how long the torch
stays on), the frame counters, and what this phone's hardware can do. Settings → **Safety
information** is the heat and battery notice, in the app, so it can be read with no network.

**Which resolution should I use?**
1080p at 30 fps for most purposes. 4K is available with Pro, but it makes the phone considerably
hotter, uses far more network bandwidth and disk space on your recorder, and adds little for a fixed
camera view. The app defaults to a middle setting derived from what your phone's lens actually
supports.

**The phone gets hot.**
Expected for continuous video encoding, and the app reduces bitrate automatically when the phone
reports thermal pressure — though at small picture sizes there is little left to reduce, so the
resolution and frame rate you choose matter far more than that reduction does. To reduce it: lower
the resolution or frame rate, use the dim-screen control, and avoid direct sunlight. A case that
traps heat makes it worse. If you have enabled "Ignore temperature" in Settings, the app holds your
chosen quality instead of protecting the phone.

Sustained heat while charging permanently reduces battery capacity, and on a battery that is old,
damaged or not a genuine Apple part heat can also cause swelling and, uncommonly, smoke or fire.
Read the full notice — in the app under Settings → **Safety information**, or at
<https://unknownalientechnologies.github.io/vantage-public/safety> — before mounting a phone
somewhere you will leave it. The "Hot" and "Too hot" indicators stay visible while the screen is
dimmed, which is the mode this page recommends for continuous running.

**Can I use it over the internet, away from home?**
Not directly, and deliberately. The app serves only your local network — there is no cloud, no
relay, no account. If you need remote access, use your recorder's own remote features or a VPN into
your home network. Forwarding these ports from the internet is strongly discouraged: the connection
is not encrypted.

**Two-way talk does not work in my browser.**
Browsers only allow microphone access on an `https://` page, and the control page is plain HTTP, so
the Hold to talk button cannot capture your voice. This is a browser rule, not a bug in the app, and
the button says so rather than failing when pressed.

Opening the page on the camera phone itself does **not** work around it, despite what an earlier
version of the tooltip suggested: reaching Safari means leaving Vantage, and the app closes its ports
when it goes to the background, because iOS revokes camera access from a backgrounded app anyway. So
`http://127.0.0.1:8081` cannot connect.

Talk does work over RTSP, via the ONVIF audio backchannel
(`Require: www.onvif.org/ver20/backchannel`), which the app advertises and accepts. The catch is that
the clients most people try **cannot send audio** — not VLC, not ffmpeg, and not ONVIF Device
Manager, which is receive-only. Software that can: **go2rtc**, **Blue Iris**, and GStreamer's
`rtspsrc backchannel=onvif`. UniFi Protect does not support two-way talk for third-party ONVIF
cameras at all, so it will not offer it.

**Recording on the phone stopped.**
Recording needs the app in the foreground with the screen on. Check the free space on the phone: the
app always leaves 2 GB free and deletes the oldest clips to stay within that and within the
retention window you chose. In the free version the retention is capped at one hour. If recording
stopped in a way it cannot recover from, the phone will have notified you — see "Will it tell me if
it stops" above.

**A clip I want will not play, or will not export.**
The clip being written now has no index in it yet, so a player cannot open it and there is nothing to
share — which is usually the one clip you want. Tap **Stop and save this clip** on the Recordings
screen: it closes that clip immediately and recording carries straight on in a new one.

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
- **The second stream depends on the first being big enough.** The camera normally offers two
  qualities — the main stream on `/stream1`, and a smaller video-only one on `/stream2`, usually
  around 848×480 at half the main frame rate, and never above 15 fps whatever the main stream
  runs at — advertised as two ONVIF profiles so a recorder can
  watch the small one live while recording the big one. It only offers the second when there is
  room for a genuinely smaller picture. The small one has to be at most about 70% of the main
  stream's longest side and still at least 320 pixels across, so if you set the main stream very
  small there is nothing meaningfully smaller to pair with it, and the camera then advertises one
  quality and does not serve `/stream2`. Two profiles claiming the same resolution is worse than
  one honest profile, because a recorder reads that as a camera with a single quality. The second
  stream halves its frame rate again once the phone is hot, and stops altogether while it is very
  hot, coming back on its own. That is the one thermal measure in the app that sheds real work
  rather than only bitrate, and "Ignore temperature" cannot switch it off.

  Recorders read the list of qualities once, when they adopt the camera. So if you change the
  resolution — or you were on the free tier and then unlocked Pro — remove the camera from your
  recorder and add it again, or it will keep using the qualities it saw the first time.
- **No two-way talk from UniFi Protect.** Protect does not support two-way audio or live audio
  playback for third-party ONVIF cameras at all, so it will never offer it. Talk works from the
  app's own web page, and from software that can send audio over the ONVIF backchannel — see
  "Two-way talk does not work in my browser" above for which clients those are.

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
is, and quoting those numbers makes it far quicker to identify. Settings → **Copy diagnostics** puts
the same summary on the clipboard, ready to paste into the email.

If the picture has frozen and you can still reach the phone from a browser, `http://<phone-ip>:8081/diag`
answers the same counters plus a plain-language verdict, and needs no password — precisely because it
is what you reach for when nothing else is working.
