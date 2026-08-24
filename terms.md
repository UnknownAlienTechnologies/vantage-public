---
layout: default
title: Vantage — Terms of Use
---

# Vantage — End User Licence Agreement and Terms of Use

Version 1.1. Effective 24 August 2026. Applies to Vantage on iOS 17 and later.

> **Before you mount a phone and leave it running, read the Safety Notice.** It is on the Safety
> screen inside Vantage, and published at https://unknownalientechnologies.github.io/vantage-public/safety. Vantage runs a phone's camera and
> video encoder continuously while the phone is plugged in. That makes heat continuously, and heat
> permanently shortens a battery's life. Sections 5 and 6 say what that means; the Safety Notice says
> it in full.

---

## 0. How to read this agreement

This agreement grants you a licence to use Vantage (section 3), says what Vantage is for and how to
install and operate it safely (sections 4 to 7), disclaims warranties and limits our liability as far
as the law actually allows (sections 11 to 14), states your rights in particular countries (sections
15 to 18), and contains the terms Apple requires every App Store licence agreement to contain.

**Section 12 lists the rights and liabilities that cannot be excluded. It overrides every other
section, including every disclaimer and every limit.** If any part of this document reads as though a
right you have under your own consumer law does not exist or does not apply, that reading is wrong.

Nothing here is intended to make us immune from being sued, and nothing here would achieve that.
Liability for death or personal injury caused by negligence cannot be excluded by a contract term or
a notice in the United Kingdom (Consumer Rights Act 2015 s 65(1)), and cannot be limited or excluded
as against an injured person under the EU product liability regime (Directive (EU) 2024/2853 Art 15).
Purporting to exclude the Australian consumer guarantees is void (Australian Consumer Law s 64).
Apple's own developer agreement forbids an over-broad exclusion. What actually reduces risk is how
Vantage behaves, the operating conditions in section 5, and the hazard information we show you in the
app before you buy Pro and before you enable the setting in section 6.4 — not the wording below.

---

## 1. Who this agreement is with

This agreement is between you and Joshua Joseph Lipovic ("the Developer", "we", "us"). **It is
concluded between you and us only, and not with Apple.** Apple is not a party to it.

We alone are responsible for Vantage and for its content. Apple has no responsibility for Vantage.

Nothing in this agreement conflicts with, or is intended to conflict with, the Apple Media Services
Terms and Conditions or the Apple Volume Content Terms, and those terms continue to apply to your
acquisition of Vantage from the App Store. Where this agreement and those terms cannot both be
given effect, those terms prevail.

By downloading, installing or using Vantage you accept this agreement. If you do not accept it, do
not use Vantage; you may request a refund from Apple in accordance with Apple's terms.

## 2. How to contact us

Questions, complaints or claims about Vantage should be directed to us, not to Apple:

- **Name:** Joshua Joseph Lipovic
- **Postal address:** PO Box 46, Douglas Park NSW 2565, Australia
- **Email:** joshualipovic@gmail.com

If you believe Vantage has damaged a device, has caused injury, or has created a risk of either,
please tell us at the address above and describe what happened. We would rather hear about it early.
Section 12 of the Safety Notice sets out what to include in a report.

## 3. Licence

We grant you a non-transferable licence to use Vantage on any Apple-branded products that you own or
control, and as permitted by the Usage Rules set out in the Apple Media Services Terms and
Conditions.

Where the Usage Rules permit it, Vantage may also be accessed and used by other accounts associated
with you via Family Sharing, volume purchasing, or as a Legacy Contact.

Vantage is licensed, not sold. We and our licensors keep all intellectual property rights in it.

You may not sublicense, rent, lend or redistribute Vantage, or remove or circumvent the in-app
purchase mechanism. You may not reverse engineer, decompile or disassemble Vantage **except** to the
extent that restriction is prohibited by law that applies to you, or that you have a statutory right
to do so — including any statutory right to decompile in order to achieve interoperability with
other software.

You must be old enough, and otherwise legally able, to enter into this agreement where you live. If
you are not, a parent or guardian must accept it and is responsible for your use of Vantage.

## 4. What Vantage is for, and what it is not for

Vantage turns an iPhone into a fixed network camera on your own local network. It serves an RTSP
video and audio stream, an ONVIF Profile S interface, a still-image endpoint and a local web control
page, so that a network video recorder or a browser on the same network can view and record it.
Nothing is sent to us, and no server of ours is involved.

**Intended use.** Vantage is intended for non-critical monitoring of your own property, on a network
you control, on a spare phone you have accepted will wear out (section 6.1), installed and operated
in the conditions in section 5. That is the use it is designed around and the use the rest of this
agreement is written around.

**What we have actually tested.** Adoption, streaming and recording have been verified against the
recorders and clients named in the App Store listing and on the support page, on the phone models and
iOS versions stated there, with the known limitations listed there. We have **not** carried out
thermal soak testing: we have not measured surface or battery temperatures on a phone running Vantage
continuously, at any configuration, and we do not present any figure about how hot a phone gets or
how long it can be run. Section 6 tells you what we do and do not know about that, and section 5
tells you how to install the phone given it.

Facts about how it works that bear on what you can reasonably expect of it:

- **Foreground only.** iOS revokes camera access from apps in the background. Vantage streams only
  while it is open in the foreground on an unlocked, awake device. It keeps the screen awake for
  that reason.
- **It requires iOS 17 or later.**
- **iOS can interrupt it at any time**, including for thermal reasons, system pressure, an incoming
  call, or another app taking the camera. Capture will resume when it can, but it can stop.
- **The free tier streams up to 640×480** and one simultaneous viewer, and keeps up to one hour of
  on-device recordings. The Pro purchase raises those limits (see section 8).
- **Resource limits apply regardless of tier.** The RTSP listener accepts a fixed maximum number of
  simultaneous connections, currently 16, whatever your tier. On-device recording deletes the oldest
  clips first to stay within a bounded amount of storage, so older footage is overwritten in normal
  operation. We may change these technical limits.
- **The local network is part of the trust boundary.** The control API and web page are plain HTTP
  with no TLS. iOS provides no certificate-generation API, so TLS on a home network would mean
  shipping a self-signed certificate and asking you to click through a browser warning; we judged
  that a worse trade-off than being explicit that the network is part of the boundary. It is a real
  gap, not an impossibility. `SECURITY.md` sets out the full model.

**Vantage is not a life-safety system, an alarm system, or a monitored security service.** It is not
designed, tested or supplied for use where a failure to capture, record, stream or alert could lead
to death, injury, or serious loss. Do not use it as the only means of monitoring anything that
matters, and do not use it in place of a smoke alarm, an alarm system, a medical or baby monitor, or
a professionally monitored service. We do not warrant that it will be recording at any given moment.

**Recording other people is your responsibility.** Laws on video and audio recording, on notifying
people that they are being recorded, and on recording in workplaces, shared buildings and public
space differ widely and some of them are criminal. Audio recording in particular is restricted in
many places even where video is not. You are responsible for having the legal right to record what
you point the camera at, and for any notice or consent your local law requires.

## 5. How to install and operate the phone

Vantage runs the camera and the hardware video encoder continuously with the screen on, and its
documentation tells you to keep the phone connected to power while it does so. That combination
generates heat continuously, for as long as you run it.

**These are instructions, not licence conditions.** Failing to follow them does not end your licence
and does not remove any right you have. They are here because they are the part of this document that
actually reduces the risk: under the EU product liability regime, whether a product is defective is
assessed partly on its presentation and its instructions for use, and on its reasonably foreseeable
use (Directive (EU) 2024/2853 Art 7(2)(a)–(b)). Clear instructions are worth more than a disclaimer.

The Safety Notice states the same hazards in more detail, with the reasoning. It is on the Safety
screen inside Vantage and published at https://unknownalientechnologies.github.io/vantage-public/safety. Read it before you mount a phone and
leave it running.

1. **Ambient temperature.** Apple states that iPhone is "designed for use where the ambient
   temperature is between 0º and 35º C (32º to 95º F)", and that "[u]sing an iOS or iPadOS device in
   very hot conditions can permanently shorten battery life". Operate the phone within that range.
   If the place you want to mount it goes above 35 °C for part of the year — a conservatory, a loft,
   a sunlit window, an outdoor housing in summer — that is a place where continuous operation will
   age the battery faster, and you should either cool it, move it, or accept that.
2. **Ventilation.** Mount the phone where air can move freely around it. Do not run it inside a
   sealed enclosure, a cupboard, a box, or under or on top of soft furnishings, bedding or clothing.
3. **No direct sunlight.** Apple lists leaving a device in direct sunlight for an extended period,
   and using the camera for an extended period in hot conditions or direct sunlight, among the
   things to avoid. Vantage's normal use is exactly extended camera use, so mount it out of the sun.
4. **Cases.** Apple states that charging a device inside certain styles of case "may generate excess
   heat, which can affect battery capacity", and to take the device out of its case if it gets hot
   while charging. Do that.
5. **Battery condition.** Do not use Vantage on a phone whose battery is swollen, damaged, leaking
   or known to be degraded, or whose screen or back is lifting, or that rocks when placed on a flat
   surface, or that iOS reports as having a battery it cannot verify as genuine. If you suspect
   damage to the phone or its battery, stop using it and have it serviced by Apple or an Apple
   Authorised Service Provider. Apple's own guidance is to discontinue use in that situation.
6. **Power supply.** Use an Apple or MFi-compliant charger and cable. Keep the phone, cable, adapter
   and any wireless charger in a well-ventilated area while in use or charging.
7. **Placement.** Mount the phone securely, where it cannot fall, and not on or against anything
   flammable. Consider what would be affected if the phone were to overheat, smoke or catch fire in
   that position.
8. **Attention.** Look at the phone in person at least once a month. Feel whether it is hotter than
   it used to be at the same settings; check the seams and the screen for the bulging described in
   the Safety Notice; check the mount and the cable. **Do not rely on the app's "Hot" and "Too hot"
   badges — they are hidden while the screen is dimmed, which is the mode we recommend for continuous
   running.** Stop and unplug the phone if it is unusually hot to touch, if the case is deforming or
   bulging, or if there is any smell, smoke or discolouration.
9. **Network access.** Anything on your network holding the API token can change Vantage's
   configuration, including settings that increase heat. You are responsible for who and what is on
   your network, for keeping the token secret, and for commands issued to the local API — see
   section 7.
10. **Legal use.** Use Vantage only in accordance with applicable law, including the recording law
    referred to in section 4.

If you cannot meet these conditions, do not run Vantage continuously on that phone in that place.

## 6. Heat, the battery, and the "Ignore temperature" setting

This section is disclosure, not an exclusion. It is here so that you know what Vantage does to a
phone before you decide how to run it.

### 6.1 What continuous operation does

Running the camera and encoder continuously, with the screen on, while connected to power, keeps the
phone warm and keeps its battery at or near a full charge. Both of those accelerate the permanent,
irreversible loss of battery capacity. Apple states that exposure to ambient temperatures above
35 °C "can permanently damage battery capacity", that "[c]harging the device in high ambient
temperatures can damage it further", and that even storing a battery in a hot environment "can
damage it irreversibly". Higher resolutions and frame rates make more heat; 4K makes the phone
considerably hotter than 1080p.

So: expect the battery in a phone dedicated to this to wear out faster than it otherwise would. That
is the near-certain outcome, and it is the reason the app is meant for a spare phone rather than one
you depend on.

Two further outcomes, less likely but on the same causal chain. Over months, a battery aged by heat
can swell, which deforms the phone and can lift or crack the screen — condition 5 above tells you
what to do if that starts. And a lithium-ion battery can vent, smoke or catch fire. That normally
requires an additional cause, such as a manufacturing defect, physical damage, or a non-genuine or
badly installed replacement battery, rather than heat alone. **We do not tell you how much margin
there is, because we have not measured it.** We have no temperature data from a phone running
Vantage, and we make no claim about how close to or far from any threshold such a phone runs. What we
do say is that sustained high temperature reduces that margin over time, which is why conditions 5
and 7 in section 5 are there.

### 6.2 What Vantage's thermal reduction is, and is not

Vantage reads the thermal state iOS reports and reduces the video bitrate it asks the encoder for
when that state rises. That is the entirety of its thermal behaviour, and it is the only thing
Vantage itself does about heat. Specifically:

- The reduction is to 60% of the target bitrate at the state iOS calls *serious* and 35% at
  *critical*, but never below 500 kbps.
- Because of that floor the reduction is small or nil at low resolutions. At the free tier's
  640×480 it is around 16%, and *critical* is no stricter than *serious*.
- The thermal state is re-read only while frames are being encoded.
- It does not reduce frame rate or resolution, does not turn the torch or the screen off, and does
  not stop capturing, at any temperature.

So it is a reduction in output quality that helps a little, at higher resolutions, some of the time.
It is not the protection that stands between a phone and overheating — the device's own protections,
described in 6.3, are — and you should not install a phone anywhere on the basis that Vantage will
manage its temperature for you.

### 6.3 What the OS does, which Vantage cannot change

An app can read the thermal state; it cannot set it, and it cannot switch off the device's own
protections. Apple documents that "iOS and iPadOS devices have built-in protections to prevent
overheating", and that above the normal operating range: charging, including wireless charging,
"slows or stops"; "[t]he display dims or goes black"; radios enter a low-power state; "[t]he camera
flash or other camera features might be temporarily disabled"; and performance is reduced. Apple
further states of its temperature-based charging protections that they "work automatically and can't
be turned off". iOS can show a temperature warning screen and shut the device down. The battery pack
has its own hardware protection. The capture system itself can shut down independently of Vantage
under system pressure, and Vantage reports that as an interruption when it happens.

None of that is affected by any setting in Vantage. Equally, none of it is a reason to run a phone
harder: those protections exist for abnormal conditions, and a camera deliberately installed so that
they engage continuously is being run outside what it was designed for.

### 6.4 The "Ignore temperature" setting

Vantage has a setting called "Ignore temperature". When it is on, Vantage holds the bitrate you chose
instead of applying the reduction described in 6.2. It is unlocked by the Pro purchase, as part of
the same entitlement as high resolution.

> **WARNING — heat, battery damage and fire hazard.**
>
> **What it does.** It disables the only thing Vantage does about heat, at every thermal state iOS
> reports, including the most severe one. With it on, Vantage asks for the same bitrate on a hot
> phone as on a cool one, for as long as it runs.
>
> **What can happen.** The phone runs hotter for longer than it otherwise would. That brings forward
> the permanent battery capacity loss described in 6.1. Over months a heat-aged battery can swell,
> deforming the phone and lifting or cracking the screen. A damaged, swollen, aged or non-genuine
> lithium-ion battery can vent, smoke or catch fire, which can cause serious injury and can damage or
> destroy the phone and property near it.
>
> **How to avoid it.** Leave this setting off. If you turn it on, do not do so on a phone whose
> battery is degraded, swollen or non-genuine, in an enclosure, in sunlight, or in a place where you
> have not thought about what happens if the phone overheats.

It does not change how iOS manages heat, and it cannot; everything in 6.3 still applies. Turning the
setting off is always available, whether or not you have bought Pro.

**One thing to know about how it is stored.** The setting is saved on the phone and restored every
time Vantage launches. It is restored without re-checking your Pro entitlement, so if it was on when
an entitlement ended it stays on until someone turns it off in the app.

## 7. Your network, and the local API

Vantage's control API and web page are reachable by anything on the same network that holds the API
token. Configuration changes made that way take effect on the phone, including changes that increase
heat.

**Bitrate and frame rate are not limited by your tier over the API.** The API accepts up to
50,000 kbps and up to 240 fps, subject only to what the lens supports, so a token-holder can drive
the phone harder than any preset in the app — on the free tier as well as Pro. Resolution and the
setting in section 6.4 additionally require Pro.

You are responsible for the security of your network, for keeping the API token secret, for the
devices and scripts you allow to hold it, and for the configuration changes made through it —
including ones made by an automation you set up, or by another person or device to whom you gave the
token. The connection is not encrypted; treat the network itself as part of the boundary.

**Checking whether the setting in section 6.4 is off.** The in-app toggle can show the setting as off
after it has been enabled over the local API, so the toggle is not a reliable check on its own. Force
quit and reopen Vantage and then look at the toggle, or read `thermal.isThrottlingIgnored` from the
local API. Do not tap the toggle to "confirm" it is off: if it is showing the wrong state, tapping it
turns the override on.

## 8. Vantage Pro (in-app purchase)

Vantage is free to download. Vantage Pro is a single non-consumable in-app purchase, product
identifier `com.joshlipovic.vantage.pro`. One purchase, no subscription. It is available to your
family group where Family Sharing applies.

What it unlocks:

- **HD and custom formats** — 720p, 1080p, and up to 4K, plus custom formats.
- **Auto light** — light up automatically when something moves in the dark.
- **API and Home Assistant** — a REST API and a flat JSON endpoint.
- **Audio and two-way talk** — audio with the video, and talk through the phone's speaker.
- **Multiple viewers** — more than one simultaneous viewer, so a recorder and a live viewer can
  watch at the same time, subject to the connection limit in section 4.
- Keeping more than an hour of on-phone recordings.
- The "Ignore temperature" setting described in section 6.4, which comes as part of the same
  entitlement as HD and custom formats.

That last item is listed here deliberately, and the same hazard information is shown to you in the
app before you buy and again before you can enable the setting. It is a heat-affecting setting
bundled with a resolution entitlement, and you should know that before you pay rather than discover
it afterwards.

**Payment, delivery and refunds are Apple's.** We do not process your payment and cannot issue a
refund; refund requests go to Apple under the Apple Media Services Terms and Conditions. Prices are
set through App Store Connect and may change.

If your entitlement lapses, is refunded or is revoked, paid features stop being available for you to
switch on. One exception you should know about: as section 6.4 explains, the "Ignore temperature"
setting is saved on the device and restored at every launch without re-checking your entitlement, so
if it was on when the entitlement ended it stays on until someone turns it off in the app. Turning it
off is always available.

## 9. Maintenance, support and updates

**We are solely responsible for providing any maintenance and support services for Vantage. You and
we acknowledge that Apple has no obligation whatsoever to furnish any maintenance and support
services in respect of Vantage.**

Support is by email at the address in section 2, from a single developer, on a best-efforts basis. We
do not promise a response time, except for the specific commitment in section 14 where section 46 of
the UK Consumer Rights Act 2015 applies.

Updates are distributed through the App Store and may change or remove features. We do not commit to
a release schedule. We do not, and cannot lawfully, disclaim responsibility for supplying updates
that are necessary to keep Vantage in conformity or to maintain its safety, where the law that
applies to you requires them; nothing in this section reduces any statutory right you have to
updates. If we become aware of a safety problem in Vantage we intend to fix it and to say so.

## 10. Warranty, and Apple's role in it

**We are solely responsible for any product warranties in respect of Vantage, whether express or
implied by law, to the extent not effectively disclaimed.**

**In the event of any failure of Vantage to conform to any applicable warranty, you may notify
Apple, and Apple will refund the purchase price of Vantage to you. To the maximum extent permitted
by applicable law, Apple will have no other warranty obligation whatsoever with respect to Vantage.
As between Apple and us, any other claims, losses, liabilities, damages, costs or expenses
attributable to any failure to conform to any warranty are our sole responsibility.**

Read that with section 12. Apple's entire obligation is a refund of what you paid — which for a
free download with one small in-app purchase is a small sum. It is not a cap on your rights against
us, and it is not the measure of what you may be entitled to if a device is damaged or a person is
hurt.

## 11. Disclaimer of implied warranties

**Your statutory rights come first.** This section applies only where, and to the extent that, the
law that applies to you permits an implied warranty to be disclaimed. It does not exclude, restrict
or modify the satisfactory quality, fitness or conformity rights you have under the UK Consumer
Rights Act 2015, the consumer guarantees under the Australian Consumer Law, the guarantees under the
New Zealand Consumer Guarantees Act 1993, or your rights under EU or EEA consumer law. Section 12
governs, and prevails over anything below.

**Subject to that, and to the maximum extent permitted by applicable law, Vantage is provided "as
is" and "with all faults", without warranty of any kind, and we disclaim all implied warranties and
conditions, including the implied warranties of merchantability and fitness for a particular
purpose, and implied warranties of accuracy, quiet enjoyment and non-infringement of third-party
rights.** Some jurisdictions do not allow the exclusion of implied warranties, so this may not apply
to you at all.

In particular, and again subject to section 12, we do not promise that Vantage will be uninterrupted
or error-free; that it will be capturing, streaming or recording at any given time; that recordings
will be complete, retained for any period, or recoverable; that it will be compatible with, or be
adopted by, any particular recorder, client or third-party product, including any particular version
of UniFi Protect or any other network video recorder; that it will meet your requirements; or that
defects will be corrected. Third-party recorders and clients are outside our control and change
independently of Vantage.

This section disclaims warranties implied by law. It does not disclaim statements of fact we have
actually made. Where the law that applies to you makes information we give you about Vantage — in the
app, in its App Store listing or in its documentation — a term of your contract or relevant to the
quality you are entitled to expect, it does so, and we do not seek to displace it. If you find a
statement of ours that is inaccurate, tell us at the address in section 2 and we will correct it.

## 12. Rights that cannot be excluded

**This section overrides every other section of this agreement. Where it conflicts with anything
else here, this section wins.**

**Nothing in this agreement excludes, restricts, modifies or limits, in any amount or in any way:**

1. **our liability for death or personal injury, howsoever caused — including under any strict or
   no-fault liability regime, and including any liability of ours for gross negligence,
   recklessness or wilful misconduct;**
2. **our liability for fraud or fraudulent misrepresentation;**
3. **any liability under a mandatory product liability regime that applies to you — including
   liability under Part 3-5 of the Australian Consumer Law, which section 150 of that Law provides
   cannot be excluded, restricted or modified; liability under Part I of the UK Consumer Protection
   Act 1987, which section 7 of that Act provides "shall not be limited or excluded by any contract
   term, by any notice or by any other provision"; and liability under the EU product liability
   regime, which Article 15 of Directive (EU) 2024/2853 provides cannot be limited or excluded by a
   contractual provision as against the injured person;**
4. **any guarantee, right or remedy you have under consumer protection law that cannot lawfully be
   excluded, restricted or modified — including the consumer guarantees under the Australian
   Consumer Law, the guarantees under the New Zealand Consumer Guarantees Act 1993, the rights under
   the UK Consumer Rights Act 2015, and rights under EU and EEA consumer law; or**
5. **any other liability that cannot lawfully be excluded or restricted.**

**No limitation in this agreement applies to a claim by a person who is not a party to it.** Someone
who did not agree to this document — a member of your household, a visitor, a neighbour, a landlord,
or an insurer bringing a claim in their place — is not affected by anything in it.

**Agreeing to this document is not an acceptance of risk.** You are not, by accepting these terms, by
reading the Safety Notice, or by enabling any setting in Vantage, taken to have voluntarily accepted
any risk of injury or of damage. UK law says so expressly (Consumer Rights Act 2015 s 65(2)), and we
do not argue otherwise anywhere. The information in this document exists so you are informed before
you choose, not so that you give anything up.

## 13. Limitation of liability

**Subject to section 12 in every case.** Each paragraph below is a separate limitation, intended to
be read and applied separately; see section 24.

**13.1 Death and personal injury.** Our liability for death or personal injury is **not limited by
this agreement in any amount or in any way**. Nothing in 13.2 to 13.5 applies to it.

**13.2 Damage to a device or other property.** If you are a consumer, we do not exclude or limit our
liability for damage to your device, its battery, or any case, mount, charger, cable or enclosure you
use with it, where that damage is caused by Vantage and is of a kind that would not have occurred if
we had exercised reasonable care and skill. A claim of that kind is dealt with under section 14 and
under the law that applies to you, and **the cap in 13.4 does not apply to it**. Where you are not a
consumer, our liability for damage to property is limited as set out in 13.4.

**13.3 Business and non-consumer use.** **This paragraph applies only where you are not a consumer
under the law that applies to you.** In Australia you may be a consumer under section 3 of the
Australian Consumer Law even if you acquire Vantage for business purposes, because the amount paid
does not exceed the prescribed threshold; where that is so, this paragraph does not apply to you and
sections 12 and 15 govern. Where it does apply: to the maximum extent permitted by applicable law, we
are not liable to you for loss of profit, loss of business, loss of revenue, loss of anticipated
savings, loss of goodwill, business interruption, loss of or corruption of data or recordings, or any
indirect or consequential loss, however arising.

**13.4 Cap on financial loss.** To the maximum extent permitted by applicable law, and **other than
for the liabilities in section 12, section 13.1, section 13.2, section 14 and section 15**, our total
aggregate liability to you for financial loss that does not consist of personal injury or of damage
to property is limited to the greater of (a) the total amount you have paid for Vantage and for
in-app purchases in Vantage, and (b) fifty United States dollars (US$50) or its equivalent in your
local currency. This limit is cumulative: it is not increased by there being more than one incident
or claim. It does not apply to any liability of ours for failure to comply with a consumer guarantee
or a statutory quality or safety right.

**13.5 Contributing causes outside our control.** To the maximum extent permitted by applicable law,
and subject to sections 12, 13.1, 13.2 and 15, we are not liable for loss to the extent it is caused
by a battery, charger, cable, case, mount or enclosure that is damaged, non-genuine or not compliant
with Apple's requirements, or by a third-party recorder, client or app malfunctioning in a way we
could not reasonably have anticipated. **Nothing in this paragraph excludes liability for loss caused
by our own negligence, including in the design of Vantage or of its local API, or reduces any
liability under a mandatory product liability regime.**

Where loss is caused wholly or partly by use of Vantage outside the instructions in section 5, that
is relevant to what caused the loss and to any apportionment, on the facts and under the law that
applies to you. **That is a question of causation, not an exclusion of liability, and we do not put
it forward as one.**

**Where a limitation in 13.2 to 13.5 is not permitted by the law that applies to you, that
limitation does not apply to you and the remainder of this section continues to apply.**

## 14. If Vantage damages your device or your recordings

If Vantage causes damage to a device or to other digital content belonging to you, and the damage is
of a kind that would not have occurred if we had exercised reasonable care and skill, tell us at the
address in section 2 with a description of what happened and, if you can, the phone model, the
settings in use, and whether the setting in section 6.4 was on.

For users in the United Kingdom, this is your right under section 46 of the Consumer Rights Act 2015.
Where that section applies, we will either repair the damage — bearing any necessary costs, including
labour, materials and postage — or compensate you for it with an appropriate payment. We will do that
without undue delay and in any event within 14 days of the day we agree you are entitled to a remedy,
and we will not charge you a fee for it. **We do not exclude or restrict our liability under section
46, and nothing in this agreement should be read as doing so.**

For users elsewhere, we will handle a claim of this kind in the same spirit as a matter of policy —
though the 14-day period above is a requirement of UK law rather than a commitment we make everywhere
— and without prejudice to whatever rights you have under your own law. In the European Union those
include a claim for damage to property other than Vantage itself, and for the destruction or
corruption of data not used for professional purposes, under the mandatory product liability regime
(Directive (EU) 2024/2853 Art 6), which cannot be excluded by this agreement. Your recordings are
data of that kind.

This section describes how we will handle a claim under section 46 of the Consumer Rights Act 2015
and equivalent local law. It is not, and is not intended as, a written warranty within the meaning of
the US Magnuson-Moss Warranty Act, a warranty against defects under the Australian Consumer Law, or a
guarantee of any level of performance.

Some loss of battery capacity is an ordinary consequence of running a phone as a continuous camera,
and section 6.1 explains why. **Whether the capacity loss or other damage you experience is ordinary
wear, or a failure of the quality, safety or durability Vantage owed you, is a question of fact
decided under the law that applies to you and not by this agreement.** Nothing in this section limits
the durability or acceptable-quality guarantees you have, or our liability under section 46 of the
Consumer Rights Act 2015 or any equivalent right.

## 15. Australia

**Our goods and services come with guarantees that cannot be excluded under the Australian Consumer
Law. For major failures with the service, you are entitled to cancel your service contract with us
and to a refund for the unused portion, or to compensation for its reduced value. You are also
entitled to be compensated for any other reasonably foreseeable loss or damage. If the failure does
not amount to a major failure, you are entitled to have problems with the service rectified in a
reasonable time and, if this is not done, to cancel your contract and obtain a refund for the unused
portion of the contract.**

**Our goods come with guarantees that cannot be excluded under the Australian Consumer Law. You are
entitled to a replacement or refund for a major failure and to compensation for any other reasonably
foreseeable loss or damage. You are also entitled to have the goods repaired or replaced if the goods
fail to be of acceptable quality and the failure does not amount to a major failure.**

Computer software is "goods" under the Australian Consumer Law, and the acceptable quality guarantee
includes that goods are safe and durable. Nothing in this agreement excludes, restricts or modifies
those guarantees, or any liability of ours for failing to comply with them.

In particular:

- We do not rely on any limitation of our liability to repair, replacement, re-supply or refund,
  because that limitation is not available for goods or services of a kind ordinarily acquired for
  personal, domestic or household use, and Vantage is that kind of product.
- **The monetary cap in section 13.4 does not apply to, and we do not rely on it in respect of, any
  liability of ours for failure to comply with a consumer guarantee under the Australian Consumer
  Law, or any liability under Part 3-5 of that Law** (liability for goods with a safety defect,
  which section 150 provides cannot be excluded, restricted or modified). For consumers in
  Australia, section 13.4 is limited to claims that are of neither kind.
- You may be a consumer under section 3 of the Australian Consumer Law even if you acquired Vantage
  for the purposes of a business, because the amount paid does not exceed the prescribed threshold.
  Where that is so, section 13.3 does not apply to you.

## 16. New Zealand

If you are a consumer in New Zealand, the Consumer Guarantees Act 1993 applies and nothing in this
agreement contracts out of it. Where the acceptable quality guarantee applies, it includes that goods
are safe and durable, and computer software is goods for these purposes.

If you acquire Vantage in trade, some provisions of the Consumer Guarantees Act 1993 and the Fair
Trading Act 1986 may not apply to you as a matter of law. **We do not contract out of either Act, and
nothing in this agreement should be read as attempting to.**

## 17. European Union, European Economic Area and United Kingdom

If you are a consumer resident in the EU, the EEA or the UK:

- Nothing in this agreement affects your rights under mandatory consumer protection law in your
  country of residence, and the choice of law in section 25 does not deprive you of those rights.
- You may bring proceedings in the courts of the country where you are resident, and the choice of
  forum in section 25 does not prevent that.
- Liability under the EU product liability regime cannot be limited or excluded by a contractual
  provision (Directive (EU) 2024/2853 Art 15), and in the UK liability under Part I of the Consumer
  Protection Act 1987 cannot be limited or excluded by any contract term, notice or other provision
  (s 7). This agreement does not attempt either.
- Where the meaning of a term in this agreement is in doubt, the interpretation most favourable to
  you prevails.
- You keep any statutory right to withdraw from the purchase; refunds are handled by Apple as set out
  in section 8.

## 18. United States

If you are a consumer in the United States: nothing in this agreement limits our liability for
personal injury, and the limitation in section 13.4 does not apply to a claim for personal injury or
to a claim for damage to your property. Some states do not allow the exclusion of implied warranties
or the limitation of certain damages, so some of sections 11 and 13 may not apply to you. In
California, a term purporting to exempt a party from responsibility for its own wilful or negligent
injury to the person **or property** of another is against the policy of the law (Cal. Civ. Code
§ 1668), and a limitation of consequential damages for injury to the person in the case of consumer
goods is invalid unless proved not to be unconscionable; sections 11 and 13 are to be read
accordingly, and neither applies to injury to the person or to property caused by our negligence.

This agreement contains no arbitration clause and no class action waiver. That is deliberate: a
worldwide arbitration clause is unenforceable against consumers in several of the markets Vantage is
sold in and is itself a candidate unfair term there, and we would rather have one document that says
the same thing everywhere.

## 19. Legal compliance

You represent and warrant that you are not located in a country that is subject to a U.S. Government
embargo, or that has been designated by the U.S. Government as a "terrorist supporting" country, and
that you are not listed on any U.S. Government list of prohibited or restricted parties.

## 20. Intellectual property

If any third party claims that Vantage or your possession and use of it infringes that third party's
intellectual property rights, **we, and not Apple, are solely responsible for the investigation,
defence, settlement and discharge of any such intellectual property infringement claim.**

## 21. Product claims

You and we acknowledge that **we, and not Apple, are responsible for addressing any claims of yours
or of any third party relating to Vantage or your possession and/or use of Vantage, including but not
limited to: (i) product liability claims; (ii) any claim that Vantage fails to conform to any
applicable legal or regulatory requirement; and (iii) claims arising under consumer protection,
privacy, or similar legislation.**

That allocation is between us and Apple. It does not reduce anything you are entitled to, and it does
not stop you from pursuing any remedy you have against anyone. Where you have a claim, direct it to
us at the address in section 2.

## 22. Third-party terms, and Apple as third-party beneficiary

You must comply with any applicable third-party terms of agreement when using Vantage. That includes
the terms of any network video recorder, home automation platform or other product you connect it to;
your wireless data service agreement; and any rules that apply where you install the phone, such as a
tenancy agreement, a workplace policy, or a building or homeowners' association rule.

**Apple and Apple's subsidiaries are third-party beneficiaries of this agreement, and upon your
acceptance of it Apple will have the right (and will be deemed to have accepted the right) to enforce
this agreement against you as a third-party beneficiary of it.** Apple requires this clause in every
App Store licence agreement. It gives Apple no right against you that we do not have, and it does not
reduce any right of yours against us or against Apple.

## 23. Reimbursement for deliberate unlawful use

Where you deliberately or recklessly use Vantage unlawfully — in particular to record, retain or
distribute images or audio of people without the legal right to do so, or in breach of section 19 —
and a third party brings a claim against us as a result, you will reimburse us for the reasonable and
properly evidenced costs we incur, provided that we notify you promptly, allow you to participate in
the defence, do not settle without your consent, and take reasonable steps to mitigate.

This does not apply to a claim for death or personal injury, to a claim arising from our own
negligence or breach of this agreement, or where the law that applies to you does not permit such a
term. If you are a consumer and this term is unfair or unenforceable under the law that applies to
you, it does not apply to you and the rest of this agreement continues to apply.

## 24. Severance, and how these terms are meant to be read

This agreement is drafted so that an unenforceable part can be removed without taking the rest with
it.

Each section, each paragraph, each sentence and each limb of a list in this agreement is a separate
provision. If any of them is held to be void, unenforceable, unfair or prohibited under the law that
applies to you — whether wholly or in part, and whether generally or only as applied to you — then to
the extent of that finding it is severed and does not apply, and every other provision continues in
full force. Where a provision would be enforceable if part of it were removed or its scope narrowed,
it applies with that part removed or that scope narrowed.

No exclusion or limitation in this agreement is to be read as applying to a liability described in
section 12. If a provision could be read either as excluding such a liability or as not excluding it,
the second reading is the intended one.

Failing to enforce a term is not a waiver of it. Headings are for convenience.

## 25. Governing law and forum

This agreement is governed by the laws of New South Wales, Australia, and the courts of New South Wales, Australia have
jurisdiction, **except that:**

- this does not affect any mandatory consumer protection law of your country of residence that
  applies to you, and does not deprive you of the protection of provisions that cannot be derogated
  from by agreement under that law; and
- if you are a consumer, you may bring proceedings in the courts of the country where you are
  resident, and we will bring any proceedings against you there.

Vantage is distributed worldwide through the App Store, so it is directed at every country it is
available in. The choice above therefore settles less than it appears to, and section 12 rather than
section 25 is what determines whether an exclusion works.

## 26. Termination

This agreement applies until terminated.

Your licence ends if you materially breach section 3 or section 19. It also ends if you delete
Vantage from all your devices, and you may end it at any time by doing so. **The instructions in
section 5 are not licence conditions, and not following them does not end your licence.**

We may cease to distribute or support Vantage, and Apple may remove it from the App Store. Either can
happen without our agreement.

On termination you must stop using Vantage and delete it. Sections 5, 6, 10 to 25, 27 and 29 survive
termination. Termination does not affect any right or remedy you had before it, and does not affect
anything in section 12.

## 27. Privacy

Vantage collects nothing: no analytics, no tracking, no advertising, no account, and no telemetry.
Video, audio and settings stay on the device and on your own network. The Privacy Policy explains
exactly what the app accesses, what is stored on the device, and what leaves it, and is published at
https://unknownalientechnologies.github.io/vantage-public/privacy. It forms part of your agreement with us.

## 28. Changes to this agreement

We may change this agreement for a future version of Vantage. The version that applies to you is the
one published when you download or update Vantage, and material changes will be identified by the
version and date at the top of this document. If you do not accept a change, stop using the version
it applies to.

## 29. Language, transfer, and entire agreement

This agreement was written in English. Where a translation is provided and the two differ, the
English version is the one we drafted and the one we can answer questions about — but if the law
that applies to you gives the translation in your own language precedence, that law prevails.

We may transfer our rights and obligations under this agreement to someone else, for example if
Vantage changes hands. If we do, it will not reduce your rights under this agreement or under the
law that applies to you, and we will say so in the app or its listing. You may not transfer your
licence except as section 3 allows.

This agreement and the Privacy Policy are the whole agreement between you and us about Vantage, and
replace Apple's standard Licensed Application End User Licence Agreement in respect of Vantage. The
Safety Notice is information we give you about safe use, not a source of obligations on you. Nothing
in this section limits any liability for fraud or fraudulent misrepresentation, or excludes any
statutory right you have in respect of a pre-contractual statement.
