---
title: "The cloud dependency test: what dies when the internet does"
description: "A five-minute test that tells you exactly how fragile your smart home really is — and which devices to stop trusting with anything that matters."
category: "Local vs Cloud"
date: 2026-07-10
readingTime: "6 min"
---

Every smart home marketing page says "works locally" or "responds instantly." Almost none of them mean it the way you'd assume. Here's a test that cuts through all of it in about five minutes, using nothing but your fingers and your router.

## The test

Pull the internet. Not the Wi-Fi — the *internet*. Unplug the WAN cable from your router, or disconnect your modem, so your home network is still up but has no path to the outside world.

Then walk your house and try everything:

- Flip the lights from a switch and from the app
- Trigger a motion-based automation
- Lock and unlock a smart lock
- Open the camera feed
- Ask your voice assistant to do something

Make a note of what still works and what doesn't. That list is the truth about your smart home, and it's usually nothing like what the boxes promised.

## What you'll probably find

Three buckets emerge every time.

**Still works, instantly.** Thread and Zigbee devices bound locally, Z-Wave gear, anything running through a local hub. These don't care that the internet is gone because they never needed it. This is the local-first core.

**Works, but only from a physical control.** Some devices keep functioning from a wall switch but lose app control, because the app talks to a cloud that talks back to the device — a round trip out of your house and back, for a device sitting ten feet away.

**Completely dead.** Cloud-only devices. The app spins, the voice assistant apologises, nothing happens. These are the ones marketing called "smart" and reality calls "a paperweight during an outage."

## Why the round trip matters even when the internet is up

Here's the part people miss: a cloud-dependent device isn't just fragile during an outage. Every single command it handles, even on a perfect day, takes a trip to a server somewhere and back. That's the lag you feel when a light stutters before responding. Local devices don't have that lag because there's no round trip — the command never leaves your house.

So the internet-off test isn't only about outages. It's a proxy for *everyday* responsiveness. The devices that die when the internet's gone are the same ones adding latency when it's fine.

## What to actually do with the results

You don't need to rip out every cloud device — some genuinely need the cloud, and that's a fair trade for the right job. The point is to make it a *decision* instead of an accident.

- Anything load-bearing — lights you rely on, locks, safety-adjacent automations — should land in the "still works instantly" bucket. If it doesn't, that's your next fix.
- Cloud-only devices are fine for the non-critical edges: a novelty light, a nice-to-have notification.
- Every cloud device you keep should ideally have a local fallback — a physical switch, a manual override — so an outage degrades your home instead of breaking it.

## The takeaway

Run the test once. It's genuinely uncomfortable the first time, because most people discover their "smart home" is far more cloud-dependent than they believed. But you can't fix a fragility you can't see, and five minutes with an unplugged WAN cable shows you all of it at once.

*Want the structured version? The reliability checklist turns this into a device-by-device audit you can actually work through.*
