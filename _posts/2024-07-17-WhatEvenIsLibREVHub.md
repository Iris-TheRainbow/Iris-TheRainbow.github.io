---
title: What even is LibREVHub?
date: 2024-07-17 19:36:00 -0500
categories: LibREVHub
tags: LibREVHub
---

# LibREVHub?
LibREVHub is the project to make the controls from the REV Hub Interface available as a sdk that would enable easy control of a REV Expansion Hub over USB.

While not everything is complete and final intents are done, I do think that this is worth writing. So, what exactly is LibREVHub? What does it do? why?
## What is it?
At its very core, LibREVHub is a python library that implements the REV libraries available when we decompiled and updated REV Hub Interface. That is its own can of worms
and I will probably get to writing about it at some later point in time. However, LibREVHub is more than than what we are still using (at time of writing) as the comms for
RHI (REV Hub Interface), which those themselves are basically just the comms that were used by REV in their offical releases of RHI.

LibREVHub is intended for release as a library that anyone can use to control their Expansion Hub, and with that it features many quality of life improvements. Most
importantly, there are docstrings for every. single. function. in. that. damn. thing. Which, idealy would make it much, much easier for users to program themselves. On top of
this, every. single. one. has (or will have soon) type hints for their inputs paramaters and returns. (Can you tell that there was a lot of them to document?)

## What does it do?
LibREVHub will primarily be two componets. First, there is the communications stack and basic hardware support. This is what RHI uses, but would not be the most user friendly.
The second, and in my oppinion more interesting part of this is the LibREVHub SDK. The SDK is much more similar to the FTC Robot Controller's user facing APIs and would be much
easier to program with. You can expect device classes that are pretty close to the FTC Robot Controller's classes.

## Why would you even use this?
Well, for one, the current REV Hub control system is not going to last forever. We already know that the control system would be swapped for the 2027-2028 FTC season and that
mean many, many parts of the REV conrol system would have very few uses. This, at least personally, is a primary goal with LibREVHub. It means that these (honestly, they're
really impresive hobby robotics platforms) hubs will be usless without software to control thim. Like this, you can connect a rev hub to a comuputer, Raspberry Pi, or any
other device you may want and control it without much hassle.
