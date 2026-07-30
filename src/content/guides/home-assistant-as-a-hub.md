---
title: "You're using Home Assistant as a hub. Here's the problem."
description: "Home Assistant is brilliant. But treating it as the hub that everything routes through is how you build a single point of failure into a system you chose for its reliability."
category: "Home Assistant"
date: 2026-07-15
readingTime: "9 min"
---

Strong opinion up front: Home Assistant should almost never be the thing your smart home depends on to function. It should be the thing that makes your smart home *better* while your devices stay independently reliable underneath it.

If that sounds backwards, stick with me — this is the mistake that turns a powerful tool into your home's weakest link.

## The seductive wrong turn

Home Assistant can talk to everything. Zigbee, Z-Wave, Matter, Thread, cloud APIs, obscure protocols nobody else supports. So the natural instinct is to route *everything* through it: every device, every automation, every integration living or dying by that one box.

The problem is that you've now built a system where a single Raspberry Pi reboot, a bad update, or a corrupted SD card takes down your entire home. Lights, locks, the lot. You picked Home Assistant partly for reliability and control, and then handed it a single point of failure it was never meant to be.

## The distinction that fixes it

There's a difference between *bridging* and *depending*.

**Depending** is when the light only turns on because Home Assistant received the motion event, evaluated an automation, and sent the command. Kill Home Assistant and that light is dead.

**Bridging** is when your Thread or Zigbee devices are grouped and reliable on their own, and Home Assistant sits alongside them adding logic, dashboards, and the clever cross-ecosystem automations — but the core stuff keeps working if HA is down for maintenance.

The reliable design keeps the load-bearing automations as local as possible on the devices themselves, and uses Home Assistant for what it's uniquely good at: the things no native ecosystem can do.

## Local vs cloud isn't the only axis

Everyone talks about local versus cloud. But there's a second axis people miss: **local-but-centralised** versus **local-and-distributed**.

Home Assistant running everything is local — nothing leaves your house. It's also completely centralised, so its reliability is capped by one device's uptime. A Zigbee group bound directly, or a Thread group firing locally, is local *and* distributed — no single box has to be alive for it to work.

Cloud dependency is the obvious risk. Centralisation is the quiet one. A lot of "local-first" setups are actually one SD card away from total failure, and their owners don't find out until update night.

## What a resilient setup looks like

The pattern that holds up:

- Core, safety-adjacent automations (lights on a switch, a lock's own logic) stay local to the device or ecosystem
- Home Assistant layers on top for presence, cross-vendor logic, notifications, dashboards
- If Home Assistant goes down, the house degrades gracefully instead of going dark

That's the whole philosophy: Home Assistant as an enhancement, not as the foundation the house stands on.

## The takeaway

Ask one question of every automation you build: *if Home Assistant were down right now, what would stop working — and is that acceptable?* If the answer includes your lights or your locks, you've turned a bridge into a dependency. Move those back down to the devices, and let Home Assistant do the clever stuff on top.

*This "what dies if X goes down" test is the backbone of the reliability checklist — it's how you find the single points of failure before they find you.*
