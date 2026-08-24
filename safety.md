---
layout: default
title: Vantage — Safety Information
---

# Important safety information

**Vantage — iPhone IP camera. Read this before you mount a phone and leave it running.**

Version 1.0. Effective 24 August 2026. Applies to Vantage on iOS 17 and later.

**What this document is.** It explains the physical risks of running a phone as a continuous camera,
and how to reduce them. It is drawn from Apple's published documentation and peer-reviewed battery
research, cited at the end so you can check it. It is not a waiver: nothing in it excludes or limits
any right you have under the consumer law where you live, and nothing in it means you have accepted
any risk. Before you start, read §6 — it lists the phones that must not be used for this at all.

**How it fits with the licence terms.** The physical instructions here are incorporated into
`TERMS.md` as conditions of use (see `TERMS.md` §5). Nothing here allocates risk, transfers
responsibility, or takes anything away. Where this document and `TERMS.md` appear to disagree about
anything — a physical instruction or a legal one — the reading more favourable to you is the one that
applies.

---

## Why this document exists, and what it is honest about

Vantage asks you to do something Apple's own guidance tells you to avoid: run the camera
continuously, with the screen on, plugged in, for days or months at a time. That is not an accident
of how people use it — it is the documented way to use it, and it is written into the setup wizard
and the support page. So the heat it produces is a designed-in consequence, not misuse, and it is
described here rather than left for you to discover.

The honest core of this document is one sentence: **running a phone this way will wear its battery
out faster than normal use, and that is the expected outcome rather than a remote risk.** Everything
else here is either detail on that, or the much rarer path by which heat contributes to something
worse.

**This does not transfer responsibility to you.** A warning is not a substitute for a safe design,
and telling you about a hazard does not discharge the obligation to reduce it. Where a hazard here
can be engineered out of the app, the fix belongs in the app; §11 lists the ones still outstanding,
which are commitments on us rather than instructions to you.

Written in the same register as `SECURITY.md`: it explains the reasoning, gives the numbers where
numbers exist, and lists what is genuinely uncertain instead of smoothing it over.

**Where to find this.** Published at https://unknownalientechnologies.github.io/vantage-public/safety and in the app's source repository at
`Legal/SAFETY.md`, in English only. At the time of writing the app does not yet link it and the store
listing does not yet summarise it — a notice nobody is shown is not doing its job, so both are in §11.

## The severity ladder, in one place

Everything below sorts into three rungs. They are stated together here because the difference
between them is the part most often lost, in both directions:

1. **Expected, effectively certain — permanent loss of battery capacity.** This happens. It is the
   normal outcome of this use pattern, not a fault (§2, §4).
2. **Plausible over months to years — swelling.** Not every phone, but common enough that you must
   know the signs and stop when you see them (§5).
3. **Rare, and needing a second cause — venting, smoke or fire.** On published cell research, heat
   alone on a healthy stock phone is unlikely to get there; it generally needs a damaged, defective,
   counterfeit or badly replaced battery as well. That is why §6 is written as conditions on the
   *phone* rather than as a temperature limit — and why it matters that the phone this app is aimed at
   is an old one. Note also that long hot operation slowly reduces the gap between rungs 2 and 3 (§6).

## How to read the alerts

The hazard alerts below follow the ANSI Z535 convention, which pairs a signal word with a stated
consequence and a stated way to avoid it:

- **⚠ WARNING** — a potentially hazardous situation which, if not avoided, could result in death or
  serious injury. It carries the safety alert symbol (⚠).
- **NOTICE** — damage to property or equipment, with no injury pathway, and so no alert symbol.

Every section that feeds the injury pathway carries a WARNING, including the two describing the app's
own ordinary operation (§1 and §2): sustained heat and sustained full charge are what produce the
swelling in §5 and erode the margin described at the end of §6, so signalling them as mere property
damage would understate them. Only §4 — capacity loss, with no route to injury — is a NOTICE. DANGER
and CAUTION are not used: harm here is not imminent, and none of it is minor.

---

## 1. Sustained heat from continuous encoding

> ### ⚠ WARNING
>
> **Hazard.** Vantage encodes video continuously in hardware, keeps the display awake, and runs with
> the phone plugged in. The system-on-chip, the display and the charging circuit all produce heat at
> the same time, indefinitely.
>
> **Consequence.** The phone will run warm to hot for as long as it is streaming. Sustained heat
> permanently degrades the battery (§4), over time causes swelling (§5), and swelling is the point at
> which a wear problem becomes a burn-and-fire problem (§6). Higher resolutions and frame rates
> produce more heat; 4K is the hottest configuration the app offers and is noticeably hotter than
> 1080p.
>
> **How to avoid it.** Use the lowest resolution and frame rate your recorder is happy with — these
> are the settings that decide how hot the phone runs. Use the **Dim the screen** control. Mount the
> phone where air can move around it. Take the case off. Keep it out of direct sunlight. See §10 for
> a full recommended configuration.

Apple states that iPhone and iPad "are designed for use where the ambient temperature is between 0º
and 35º C (32º to 95º F)", and names two of Vantage's core behaviours — "using the camera for an
extended period of time" and streaming high-quality video — among the things to avoid doing in hot
conditions or direct sunlight. Vantage does not get an exemption from that guidance because it is
useful. **Keep the ambient temperature around the phone between 0 °C and 35 °C.** Warmer than that
is outside the range the manufacturer designed for, and the consequences below get materially worse.

What the app does about heat, stated precisely. It lowers the video bitrate when iOS reports thermal
pressure — to 60% of the target at the `serious` state and 35% at `critical`, with a floor of
500 kbps below which it will not go. That is a quality reduction with a modest thermal benefit. It
does not reduce frame rate or resolution, does not turn the display off, and never stops capture, and
at low resolutions the 500 kbps floor means the reduction is small or nil. So it is not a substitute
for the placement and settings choices in §10, and it is not what keeps the phone inside its limits —
that is iOS and the hardware (§8).

## 2. Continuous charging, and why hot plus full is worse than either

> ### ⚠ WARNING
>
> **Hazard.** The recommended way to run Vantage keeps the phone plugged in permanently, so the
> battery sits at or near 100% charge while it is warm. Heat and high state of charge each accelerate
> battery ageing, and they compound.
>
> **Consequence.** Permanent, unrecoverable loss of battery capacity — faster than the same phone
> would lose it sitting in a drawer or in a pocket. Apple states plainly that "using an iOS or
> iPadOS device in very hot conditions can permanently shorten battery life", that ambient
> temperatures above 35 °C "can permanently damage battery capacity", and that "charging the device
> in high ambient temperatures can damage it further". Beyond capacity loss, this is the specific
> condition that drives the swelling in §5 and, over a long period, the loss of safety margin
> described at the end of §6.
>
> **How to avoid it.** You cannot avoid it entirely — the app needs mains power. You can reduce it:
> keep the phone cool and ventilated, and use a charge limit if your phone has one. Apple's
> user-selectable 80% charge limit (Settings → Battery → Charging) exists only on iPhone 15 and later,
> so on the older phone this app is aimed at it will usually not be there, and there is no equivalent.
> Optimised Battery Charging is not a charge limit and does nothing for a phone that is never
> unplugged. If you cannot set a limit, temperature is the only lever you have left, which makes §3
> matter more rather than less.

The mechanism, for anyone who wants to check the reasoning. The dominant ageing process in a phone
that is rarely discharged is calendar ageing: the passivation layer on the anode keeps growing,
consuming lithium and electrolyte. Its rate follows an Arrhenius temperature dependence, and with the
activation energies measured for these cells that works out at roughly a **doubling of the ageing
rate for every 10 °C** across the range a phone actually sees. Independently, a low anode potential —
which is what a full battery means — accelerates the same process, and published storage studies
find high temperature and high state of charge acting together rather than merely adding up.

So the specific condition this app creates, hot *and* full *and* continuously, is the worst of the
common combinations for battery life. That is not a reason not to use the app. It is a reason to
choose the phone accordingly and to expect the outcome.

Note also that Apple's cycle-count ratings — designed to retain 80% of original capacity at 500
complete charge cycles for iPhone 14 and earlier, 1000 cycles for iPhone 15 models — describe cycling,
not this. A Vantage phone accumulates few cycles and a great deal of hot calendar time, so those
figures are not a useful prediction of how long its battery will last.

## 3. Ventilation, cases, enclosures, sunlight and dashboards

> ### ⚠ WARNING
>
> **Hazard.** Anything that traps heat around a charging, encoding phone — a thick or insulating
> case, a sealed enclosure or junction box, bedding or soft furnishings, a car dashboard, direct
> sunlight through glass — raises its internal temperature well beyond what the same phone would
> reach in open air.
>
> **Consequence.** Rapid and permanent battery capacity loss; over time, swelling (§5); and in
> combination with a damaged, degraded or non-genuine battery, a route towards venting, smoke or
> fire (§6). Trapped heat is the single factor most under your control and the one that changes the
> outcome most.
>
> **How to avoid it.** Mount the phone in open air with clearance on the back. Remove the case, or
> use one that does not cover the back — Apple's own guidance is that if the device gets hot while
> charging, take it out of its case. Do not put a Vantage phone in a sealed enclosure, a wall box,
> a soft bag, bedding, or under anything. Do not mount it in direct sunlight or behind glass in
> sunlight. Do not use a car dashboard or a windscreen mount: an unventilated car interior in the
> sun goes far above 35 °C on its own, before the phone adds anything. Weatherproof outdoor
> enclosures are especially bad, because sealing against water also seals against airflow.

Two related points on siting, both easy to get wrong:

- **Outdoors is not a supported location.** An iPhone's splash and water resistance is not a
  permanent property and decreases with age and wear, and Apple's storage range is −20 °C to 45 °C —
  wider than the 0–35 °C operating range, but not a licence to operate in it. A phone that is cold
  and wet is a different problem from a phone that is hot. Treat outdoor use as unsupported rather
  than as tested and rejected: Vantage has not been tested outdoors or in any enclosure, and no
  thermal measurement of a mounted installation has been made at all (§11).
- **Cool the room, not just the phone.** Everything in this section is about the phone's ability to
  shed heat into the air around it. If that air is already at 30 °C, there is very little headroom
  left, and none of the app-side settings in §10 will create it.

## 4. Battery capacity loss is the expected outcome

> ### NOTICE
>
> **Hazard.** Continuous hot, fully charged operation consumes battery capacity. This is wear, not a
> malfunction, and it is permanent.
>
> **Consequence.** The phone will hold less charge, and eventually much less, than it would have. No
> injury pathway — this rung of the ladder is equipment damage only. The injury pathway starts at §5.
>
> **How to avoid it.** You cannot, while running the app. You can choose which phone bears it.

**If the phone's battery life matters to you, use a different phone.** If it is a spare you still
expect to travel with, or one you plan to sell or trade in, or one that belongs to somebody else,
this is the wrong use for it. Choose the device on that basis.

That is a description of what happens, not an allocation of responsibility, and reading it does not
mean you have accepted anything — under the law of many countries, including the UK (Consumer Rights
Act 2015 s 65(2)), a person is not taken to have voluntarily accepted a risk merely because they
agreed to or knew about a term or a notice.

Nor does this notice decide whether any particular outcome is a quality or durability failure.
Durability is expressly part of the statutory quality standard in the UK (CRA 2015 s 34(3)) and in
Australia, and your rights against Apple under its own hardware warranty or AppleCare are not ours to
describe. If you think your phone has degraded beyond what is described here, or that Vantage has
damaged it, tell us at §12, which also says what you are entitled to.

## 5. Swelling — the point at which to stop

> ### ⚠ WARNING
>
> **Hazard.** Prolonged hot, high-charge operation causes gas generation and internal expansion in a
> lithium-ion cell. A swelling battery pushes the phone apart from the inside.
>
> **Consequence.** A swollen cell has already lost mechanical integrity. Continued use, continued
> charging, or any pressure or puncture can lead to leakage of corrosive electrolyte, venting, smoke
> or fire, and injury. Swelling is the escalation that turns a wear problem into a safety problem.
>
> **How to avoid it — and what to do.** Look at the phone from time to time. Stop immediately if the
> back or the screen is lifting, a gap has opened at the seam, the display is bulging or has a
> raised area, the phone rocks when placed face-up on a flat surface, the case no longer fits, or
> the phone smells odd or is much hotter than usual for the same settings. If any of that is true:
> stop the app, unplug it, do not charge it again, do not press on the swelling and do not puncture
> or bend the device, move it away from anything flammable, and take it to Apple or an Apple
> Authorised Service Provider. Apple's own instruction is that if you suspect damage to the device
> or the battery you should discontinue use, "as it may cause overheating or injury".

Do not put a swollen phone back into service as a camera at any resolution, and do not store it in a
drawer to deal with later.

## 6. Fire — the realistic pathway, and why it runs through a bad battery

Read this section before you choose a phone, not after. It is written as a set of conditions on the
*phone*, and one of them is likely to bite: the phone this app is marketed for is an old spare, and an
old spare is exactly the phone most likely to have a degraded or third-party-replaced battery. If your
phone does not pass the checks below, the answer is a different phone, not lower settings.

> ### ⚠ WARNING
>
> **Hazard.** A lithium-ion cell can enter self-sustaining exothermic breakdown — thermal runaway —
> resulting in venting, smoke, fire and, in confined conditions, rupture.
>
> **Consequence.** Fire, burns, smoke inhalation, property damage, death.
>
> **How to avoid it.** Do not run Vantage on a phone whose battery is damaged, swollen, previously
> heat-damaged, or of unknown origin. Do not use a phone with a non-genuine replacement battery, or
> one replaced by anyone other than Apple or an Apple Authorised Service Provider. Check Settings →
> General → About and Settings → Battery for any message that iOS cannot verify a genuine Apple
> battery, and if you see one, use a different phone. Use a genuine or MFi-certified charger and
> cable. Do not use a phone with cracked glass, water damage, or a history of being dropped hard.
> Keep the phone away from flammable material. Follow §3 on ventilation, which is what keeps the
> phone far from the temperatures that matter here.

Being accurate about how likely this is, because an overstated warning is both dishonest and less
useful. In a new, healthy cell the exothermic chemistry that precedes runaway typically begins
somewhere around 90–120 °C *inside the cell*, and the self-sustaining stage typically needs
130–180 °C. Those are typical figures with a wide spread, not thresholds: reported onset temperatures
run considerably lower for some chemistries, states of charge and cell histories, and in a cell that
has been aged hot they fall further — see below. They are also cell-internal temperatures, which are
higher than anything you can feel from outside.

Against that, iOS pauses charging, dims the display, throttles the processor, shows a temperature
warning screen and finally shuts the phone down, all well before those temperatures (§8). The
realistic outcomes of this use pattern are the ones in §4 and §5 — capacity loss, then possibly
swelling — and the fire pathway in practice needs a second, separate cause: an internal short from a
manufacturing defect, physical damage from a drop or a crush, a cell that has been overcharged or
over-discharged, or a counterfeit or badly installed replacement cell that lacks the protection
circuitry and the abuse testing a genuine pack has passed. That is why this section is written as
eligibility conditions for the phone rather than as a temperature limit.

**We cannot tell you how much margin your installation has, because we have not measured any.** None
of the temperatures in this document were measured on a Vantage installation — they are Apple's design
figures and published cell research (§11). So do not read the paragraph above as a reassurance about
your phone: assume no margin, and treat §3 as the thing that creates it.

And the margin shrinks. Laboratory work on deliberately heat-aged cells finds that sustained
high-temperature ageing measurably *lowers* the temperature at which self-heating and runaway begin, so
a cell aged hot for a year has less margin than a new one. That erosion is produced by the app's normal
operation rather than by misuse, and it is the strongest reason to take §3 and §5 seriously rather than
treating capacity loss as the whole story.

**If a phone does vent, smoke or catch fire:** get everyone away from it and call the emergency
services. Do not breathe the smoke — a venting cell produces toxic gas as well as heat. Then follow
your own national fire service's guidance, which is the authority here; this notice deliberately does
not give further instructions, because we could not verify more detailed wording against a fire
authority or a manufacturer, and an unsourced instruction about a fire is worse than none (§11).

## 7. The "Ignore temperature" override

> ### ⚠ WARNING
>
> **Hazard.** With **Ignore temperature** switched on (Settings → Performance), Vantage substitutes a
> "cool" reading for the phone's real thermal state at *every* level, including `critical`. Its own
> bitrate reduction is therefore fully disabled at all temperatures, and the encoder is held at your
> chosen quality while the phone is hot, for as long as it stays hot.
>
> **Consequence.** The phone runs hotter for longer than it otherwise would, which accelerates
> everything in §4, brings §5 closer, and over a long period contributes to the margin erosion
> described at the end of §6.
>
> **How to avoid it.** Leave it off. If you switch it on, keep the phone somewhere well ventilated and
> out of the sun, check it more often for swelling, and switch it off if you cannot follow §3. It is
> not needed for normal use, and turning it off is always permitted regardless of tier.

How much this matters, stated honestly rather than dramatically. The override removes the only thing
the app itself does about heat, so it makes a hot phone hotter for longer. But what it removes is a
bitrate reduction, and encoder power scales with pixel rate rather than bit rate: **resolution and
frame rate are the settings that decide how hot the phone runs**, and the reduction this setting
defeats never touches either of them at any temperature. 4K30 is roughly twenty times the pixel rate
of the lowest setting the app offers. At low resolutions the 500 kbps floor can mean the override
changes almost nothing. So it is the most consequential setting you can change *without* changing the
picture — and choosing a lower resolution and frame rate matters more.

Three further facts about this setting, because each affects whether you can rely on what you see:

- **It is persistent, not per-session.** It is saved and restored when the app launches, so a phone
  left mounted keeps the override on across restarts indefinitely, without asking again.
- **It can be set from your network, and the displays can be wrong.** Any device holding the app's
  API token can enable it over the local HTTP API without touching the phone and without any
  confirmation. The in-app toggle may then not reflect that change, and the Diagnostics screen's
  thermal line describes the bitrate as reduced without accounting for the override, so neither
  display confirms whether the reduction is active. Those are gaps in the app, listed as outstanding
  work in §11, not responsibilities being passed to you — but until they are fixed, restrict the API
  token to devices you control, because it is something that can make the phone hotter. The one
  reliable check today is the local API: fetch `/api/state` with your token and read
  `thermal.isThrottlingIgnored`. If it reads true and you did not set it, switch the toggle on and
  then off in Settings → Performance to force it back to false.
- **It is currently sold as part of Pro, and the purchase screen does not say so.** The override is
  unlocked by the same Pro entitlement as HD and 4K, and that paywall describes resolution only. So
  somebody can buy Pro for the picture quality and unlock this without ever being told what it does.
  That is wrong, and ungating the setting is listed in §11 as outstanding work. In the meantime: if
  you bought Pro for the picture quality and have never deliberately enabled this setting, check that
  it is off by the method in the bullet above. Switching it off is free and always permitted.

## 8. What iOS does, whatever the app is set to

Vantage adjusts one thing: the bitrate of its own video encoder. No setting in the app — including
**Ignore temperature** — changes any of the following, which are iOS and hardware behaviour:

- iOS slowing or pausing charging when the phone is too warm ("Charging On Hold"). Apple states these
  protections "work automatically and can't be turned off".
- CPU and GPU throttling, display dimming, and reduced frame rates under thermal pressure.
- iOS disabling camera features, or shutting the capture session down entirely under system pressure
  — the app is told when this happens and reports it as "system pressure (heat)".
- The temperature warning screen, and thermal shutdown.
- Protection built into the battery assembly itself, which is hardware and independent of software.
  Published reviews of lithium-ion pack design describe current-interrupt devices, PTC elements, fuses
  and shutdown separators as standard practice; Apple does not publish what a given iPhone battery
  contains, so this is general engineering practice rather than a documented iPhone specification —
  and §6 explains why a counterfeit or badly replaced cell may not have it.

Two qualifications, so this is not read as more comfort than it is. Some of the above does bear on
long-term capacity, not only on immediate safety: Apple says charge pausing "helps preserve your
battery's long-term health", and that "[s]oftware may limit charging above 80% when the recommended
battery temperatures are exceeded", which mitigates part of the hot-and-full mechanism in §2. But that
is a limit on charging, not a limit on how hot the phone runs, and it will not prevent the wear in §4.

The practical consequence: switching off the app's bitrate reduction does not disable any iOS or
hardware protection. It does make the app a larger and more continuous heat source, which is what §7
is about.

## 9. Mounting, cables, unattended operation, and what not to rely on this for

> ### ⚠ WARNING
>
> **Hazard.** A mounted phone that comes loose falls. A permanently connected charging cable is a
> trip, pull and abrasion hazard, and a damaged or uncertified charger is an electrical and fire
> hazard.
>
> **Consequence.** Injury from a falling device, particularly to anyone below it; damage to the phone
> and to its battery, which brings §5 and §6 into play; electric shock or fire from a damaged cable
> or a non-compliant power adapter.
>
> **How to avoid it.** Mount to a solid surface with fixings rated well above the weight, and check
> the mount periodically — heat and vibration loosen adhesive mounts in particular. Do not mount over
> a bed, a cot, a bath, a walkway or a work area. Use a genuine Apple or MFi-certified charger and
> cable; Apple warns that adapters not meeting safety standards "could pose a risk of death or
> injury". Route the cable so it cannot be tripped over, pulled, pinched, kinked at the connector,
> crushed by a window or a door, or run under carpet. Replace any cable with damaged insulation or a
> hot connector. Keep phone, cable and adapter in a well-ventilated place.

### Not a life-safety or security system

Vantage is a single-purpose camera feed for non-critical monitoring on your own network, and it
inherits the limits of the phone it runs on. It is not a monitored alarm, not a fire or smoke
detection system, not a medical or baby monitoring device, and not suitable for anything where a
failure could cause injury, loss, or a missed emergency. That is true regardless of how you found the
app or what the store listing surfaced it for.

The failure modes are ordinary and expected, not hypothetical: iOS revokes the camera if the app
leaves the foreground, so a phone call, a notification tap or an iOS update ends the stream; iOS can
shut capture down for heat; the network can drop; the phone can restart. On-phone recording does not
stop when the disk fills — it deletes its own oldest clips to stay inside its storage budget and to
leave 2 GB free, so your retention window can be far shorter than you expect, and on the free tier it
is one hour whatever the settings say. The app provides no guaranteed uptime and no guarantee that any
particular moment is recorded. If something matters enough that missing it would cause harm or a
significant loss, use equipment built and certified for that purpose, and keep independent recording.

### Unattended operation

The intended use is an unattended phone, so the safety instructions have to survive nobody being
there. That means the conditions in §3 must be permanently true rather than true when you set it up.

Do not rely on the app's on-screen indicators. The "Hot" and "Too hot" badges are hidden while the
screen is dimmed, which is the mode this app recommends for continuous running, and the Diagnostics
thermal line does not account for the override (§7, §11). Those are gaps we have to close, not checks
you should be doing for us — but while they are open, the only trustworthy check is a physical one.
Look at the phone in person from time to time, and at least monthly: feel whether it is hotter than it
used to be at the same settings, look at the seams and the screen for the signs in §5, check the mount
and the cable. Nothing here makes that inspection a condition of anything; it is the best available
substitute for a display that currently does not work while dimmed.

A phone running Vantage should be sited on the assumption that it will one day be the thing that goes
wrong: not on or near anything flammable, not the only smoke detection in the room, and within reach
of a working smoke alarm rather than in a loft or a cupboard where a problem would go unnoticed.

### Other people in the room

Whoever installs this is usually not the only person at risk from it, and the others never read this
notice. Tell whoever else lives or works in the room what the phone is, that it is permanently
powered, and what to do if it swells, smells odd or gets much hotter than usual — unplug it if it is
safe to do so, do not press on it, and do not pick it up if it is venting or smoking (§5, §6). Do not
mount a Vantage phone somewhere a child can reach it, and do not mount it in premises you do not
control, or in a shared or rented space, without the occupier's agreement. Nothing in this notice or
in `TERMS.md` affects the rights of somebody who is harmed by the phone and never agreed to either
document — under EU product liability rules, for example, the right to compensation belongs to "any
natural person who suffers damage caused by a defective product" (Directive (EU) 2024/2853, Art 5(1)).

## 10. Recommended settings for the lowest thermal load

If the aim is to keep the phone as cool as it can be while still being useful:

**Placement**
- Ambient temperature 0–35 °C, and as far towards the cool end as the location allows.
- Out of direct sunlight and not behind glass in sun. Not in a car.
- Open air, with clearance behind the phone. No sealed or weatherproof enclosure.
- Case off, or a case that leaves the back open.
- Not on or under soft material.
- Indoors. See §3 on why outdoors is not a supported location.

**In the app**, in order of how much difference each makes to heat:
- Resolution: the lowest your recorder is content with. This is the biggest lever there is. 1080p is a
  reasonable ceiling for a fixed view; 4K30 is the hottest thing the app can do — roughly twenty times
  the pixel rate of the lowest setting — and adds little to a static scene.
- Frame rate: as low as your recorder tolerates. Lower frame rate reduces encoder work directly.
- Use **Dim the screen** whenever you are not looking at the phone. The display is a real share of
  the heat and none of the video quality.
- Torch and auto light off unless you actually need them. A running torch is a continuous heat
  source right next to the camera.
- **Ignore temperature: off.** It removes the only heat reduction the app makes for itself. It matters
  less than resolution and frame rate, and it costs you nothing to leave off.
- Bitrate: leave it on the default, which is derived from the resolution, rather than raising it. A
  manually raised bitrate increases encoder load a little.
- Record on the recorder rather than on the phone where you have the choice. On-phone recording does
  not re-encode — it writes the frames the encoder has already produced — but it adds continuous flash
  writes and file work on top of streaming, which is a real if smaller contribution.
- One viewer where one will do. Each additional RTSP client is more packetisation and more radio
  time.

**In iOS**
- A charge limit of 80%, under Settings → Battery → Charging, if your phone has one. This is an
  iPhone 15-and-later feature, so on an older phone it will usually not be there and there is no
  equivalent — Optimised Battery Charging is not a charge limit and will not help a phone that is never
  unplugged. See §2.
- Low Power Mode reduces background work and so reduces heat a little. The app does not read it and
  does not change its own behaviour because of it, and its effect on capture has not been measured
  here — try it and see whether your stream stays stable.
- Screen brightness low. The app dims the display for you, but the pre-dim level is what it returns
  to.

## 11. Outstanding work — ours, not yours

Listed in the same spirit as `SECURITY.md`. These are things wrong with the app or with how this
notice reaches you, and they are our job to fix. They are recorded here because a warning that
quietly depends on a display that is wrong is worse than no warning — not to shift the consequences on
to you.

**Design and behaviour**
- **There is no hard stop at any temperature.** The app never pauses or reduces frame rate or
  resolution for heat by itself, at any thermal state, in any tier — only iOS does. The intended fixes
  are to apply the bitrate reduction at `critical` unconditionally, regardless of the override, and to
  pause capture with an on-screen reason if `critical` persists.
- **The override is sold as part of Pro, behind a paywall that describes resolution.** It should not be
  a paid feature at all, and the intended fix is to ungate it. See §7.
- **The bitrate reduction is weak at low resolutions.** The 500 kbps floor means that on a small frame
  there is little or no reduction left to make, so the free tier is not meaningfully better protected
  than Pro. A floor set as a fraction of the requested bitrate would fix this.
- **Bitrate is not capped for heat over the local API.** A client holding the API token can set up to
  50 Mbps on any tier — more than twice the highest value the in-app picker offers — with no
  entitlement check. Frame rate and resolution over the API *are* bounded by what the lens and your
  tier allow, exactly as the in-app pickers are. Treat the token as something that can make the phone
  hotter, and expect the bitrate ceiling to be capped.
- **Enabling the override over the API is not gated or confirmed.** It can be switched on from the
  network with no acknowledgement, and it should not be.

**Displays that are wrong**
- **The thermal badge is invisible in the recommended mode.** The "Hot" / "Too hot" indicator sits in a
  strip hidden while the screen is dimmed, and dimming is what the documentation tells you to do. So in
  normal operation there is no visible heat warning on the phone. It should stay visible while dimmed.
- **The Diagnostics thermal line does not account for the override.** It describes the bitrate as
  reduced at `serious` and `critical` even when **Ignore temperature** has disabled that reduction.
  That is a wrong statement on screen, not merely a missing one, and it needs to branch on the override.
- **The in-app toggle can be stale.** A change made through the local API does not update the Settings
  toggle. Until it does, `/api/state` (`thermal.isThrottlingIgnored`) is the reliable source (§7).

**Delivery of this notice**
- **The app does not link this notice.** Nothing in the setup wizard or Settings points to it, and the
  App Store description does not summarise the heat and battery position. Both should, and the Pro
  purchase screen should state the hazard in §7 before payment rather than after.
- **It is English-only.** The app ships worldwide. Safety information should be in a language the
  reader understands (EU General Product Safety Regulation 2023/988, Art 9(7)), and translations for
  the main storefront languages do not yet exist.

**Things we do not know**
- **None of the temperatures in this document have been measured on a Vantage installation.** The
  0–35 °C range is Apple's design figure and the runaway figures come from published cell research.
  Nobody has instrumented a mounted phone running this app, so we cannot tell you how close a given
  installation runs to anything. Assume no margin (§6). That measurement should be made.
- **The emergency-response wording in §6 could not be sourced to a manufacturer or a fire authority.**
  That is why §6 now says only to get clear and call the emergency services, and refers you to your own
  fire service for the rest.
- **The app is marketed to people with an old spare phone, which is the population §6 says must not
  use it if the battery is degraded or non-genuine, and there is no check.** The app does not ask about
  battery age, replacement history or condition, and does not read what iOS knows. A first-run
  eligibility check belongs there.

## 12. If something goes wrong

Stop using the phone, unplug it, and follow §5 if there is any sign of swelling. Then tell us, so it
can be looked at and fixed for everybody.

**What you are entitled to.** Reporting a problem is not a favour to us, and it is not the same thing
as making a claim. If Vantage has damaged your phone or your recordings, `TERMS.md` §14 sets out what
we will do. In the United Kingdom that is your right under section 46 of the Consumer Rights Act 2015:
repair with any necessary costs borne by us, or an appropriate payment made within 14 days of us
accepting that you are entitled to it, with no fee charged to you — and we apply the same basis
everywhere else as a matter of policy. In Australia and New Zealand the statutory consumer guarantees
apply automatically and cannot be excluded by anything in this notice or in `TERMS.md`. In the EU and
the UK, product liability rights are not ours to limit either. Apple, separately, refunds the price of
the Vantage Pro purchase. None of that depends on you having read this document.

Email: **joshualipovic@gmail.com**
Postal: Joshua Joseph Lipovic, PO Box 46, Douglas Park NSW 2565, Australia

Please include the phone model, its iOS version, the app version, the resolution, frame rate and
bitrate you were running, whether **Ignore temperature** was on, how the phone was mounted and
whether it was enclosed or in sun, and what happened. Photographs help. Reports of overheating,
swelling or any injury are treated as a priority, and we would rather hear about a phone that got
worryingly hot than not.

---

## Sources

The factual claims above rest on the following, so they can be checked rather than taken on trust:

- Apple Support, "If your iPhone or iPad gets too hot or too cold" — 0–35 °C ambient design range;
  "using an iOS or iPadOS device in very hot conditions can permanently shorten battery life";
  charging slows or stops, display dims, camera features may be disabled, temperature warning screen.
  <https://support.apple.com/en-us/118431>
- Apple, "Batteries — Maximizing Performance" — above 35 °C "can permanently damage battery
  capacity"; charging in high ambient temperatures "can damage it further"; "[s]oftware may limit
  charging above 80% when the recommended battery temperatures are exceeded"; remove the case if the
  device gets hot while charging. <https://www.apple.com/batteries/maximizing-performance/>
- Apple, iPhone User Guide — "Set a charge limit" (the user-selectable 80% limit, iPhone 15 and later,
  under Settings → Battery → Charging). Apple does not publish a single article listing the supported
  models in a form we could quote, so the model requirement here is stated from the feature's
  availability rather than a quotation — flagged as UNVERIFIED against a primary Apple source.
- Apple, iPhone User Guide — "Understand Thermally Limited Charging on iPhone" (these protections
  "work automatically and can't be turned off"); "Important handling information for iPhone"
  (operating and storage ranges); "Important safety information for iPhone" (discontinue use if
  damage to the device or battery is suspected; battery service by a trained technician; ventilation
  while charging; adapters not meeting safety standards).
- Apple, "Batteries — Service and Recycling" — 80% of original capacity at 500 cycles (iPhone 14 and
  earlier), 1000 cycles (iPhone 15 models). <https://www.apple.com/batteries/service-and-recycling/>
- Keil et al., "Calendar Aging of Lithium-Ion Batteries: I. Impact of the Graphite Anode on Capacity
  Fade", *J. Electrochem. Soc.* 163(9) A1872 (2016), doi:10.1149/2.0411609jes — high state of charge
  as the dominant calendar-ageing stressor; square-root-of-time capacity fade.
- Mahmud et al., "Impact of temperature and state-of-charge on long-term storage degradation in
  lithium-ion batteries", *RSC Advances* (2025), doi:10.1039/d5ra03735b — temperature and state of
  charge acting together; activation energy consistent with roughly a doubling of ageing rate per
  10 °C.
- Yang et al., "A Review of Failure Modes and Safety Strategies of Lithium-Ion Batteries from
  Materials to Systems", *Adv. Sci.* (2026), doi:10.1002/advs.76228 — staged thermal runaway
  temperatures; triggers being mechanical, electrical and defect-driven; pack protection devices. The
  spread in reported onset temperatures is why §6 gives ranges rather than thresholds.
- Zhu et al., "A review of the combined effects of environmental and operational factors on
  lithium-ion battery performance", *RSC Advances* (2025), doi:10.1039/d5ra00934k — high-temperature
  ageing lowering the self-heating and runaway onset temperatures.
- ANSI Z535.4 (product safety signs and labels) and ANSI Z535.6 (safety information in manuals and
  collateral material) — signal words, the safety alert symbol, and hazard/consequence/avoidance
  structure. Edition years are not cited here because the current editions are behind a paywall and
  were not consulted directly: UNVERIFIED as to edition.
- Consumer Rights Act 2015 (UK), ss 34, 46, 47, 62, 65 — durability as part of satisfactory quality;
  the remedy for damage caused by digital content; liability that cannot be excluded; unfair consumer
  notices; and s 65(2), that a person is not taken to have voluntarily accepted a risk merely because
  they agreed to or knew about a term or notice. <https://www.legislation.gov.uk/ukpga/2015/15>
- Australian Consumer Law (Competition and Consumer Act 2010 (Cth), Sch 2), ss 18, 29, 54, 64 — as
  described by the ACCC: acceptable quality means a product "is safe, durable and free from defects",
  the guarantees "can't be taken away by anything a business says or does", and "[i]t is unlawful for
  businesses to mislead consumers about these rights".
  <https://www.accc.gov.au/consumers/buying-products-and-services/consumer-guarantees>
- Directive (EU) 2024/2853 on liability for defective products, Art 5(1) — "any natural person who
  suffers damage caused by a defective product … is entitled to compensation".
- Regulation (EU) 2023/988 (General Product Safety Regulation), Art 9(7) — instructions and safety
  information in "a language which can be easily understood by consumers".

Where a claim in this document is not supported by one of the above, it is flagged in §11 or marked
UNVERIFIED above. The legal references are cited so you can check them; they are not legal advice.

---

Again, and to be clear: this is safety information and it is not a waiver. Nothing in it excludes or
limits any right you have, and nothing in it means you have accepted any risk. Wherever Vantage is
bought, the mandatory consumer-protection and product-liability law of the country you live in applies
to it, whatever governing law `TERMS.md` names.
