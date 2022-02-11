---
layout: default
title: Main PC
has_children: false
nav_order: 1
permalink: hardware/main-pc
parent: Hardware
---

# Main PC

## The Hardware

This is my main PC, which I use for my daily work and also gaming.
You can find explanations for my decisions below.

- CPU: AMD Ryzen 9 5900X (12 cores @ 4.5 GHz)
- CPU Cooler: Noctua NH-D15 chromax.black
- RAM: 2x16 GB Crucial Ballistix DDR4 3600 MHz CL16
- Mainboard: Gigabyte B550 Aorus Pro V2
- GPU: My old GTX 1070 with 8 GB
- SSD 1: Samsung 980 Pro 1TB (OS and all Programs except games)
- SSD 2: Samsung 970 EVO Plus 1TB (VMs, git repositories, 3D modeling stuff)
- SSD 3: Samsung 870 EVO 1TB (games)
- SSD 4: Crucial MX500 1TB
- PSU: 750W beQuiet Pure Power 11 Full Modular
- Case: Corsair Obsidian 750D
- Case Fans: 3 Noctua NF-A14 PWM

## Some explanations

Yes, I have 4 TB of SSD Storage.
Why? Part of that is because I initially planned to get 3 TB, just to have enough storage and to have a NVME Gen 4 for my OS, a NVME (Gen 3 because the Chipset doesn't offer a second Gen 4 slot) for VMs and stuff and a SATA SSD for games (they don't really profit from faster NVME drives)
I also didn't want spinning disks because of the noise (the power converters in my lamps are louder than my PC at idle..).

I ordered the MX500 which was a little cheaper than the 870 EVO (although its slightly slower on paper), but also ordered the 870 EVO when its price dropped because of black friday.
I planned on returning the MX500, but as I had already written like half a terabyte on that drive, I decided to keep it.
And another Terabyte of SSD Storage never hurts :D

To the RAM:
The larger Ryzen processors have two partitions on one chip, which are connected using what AMD calls "infinity fabric".
The clock frequency of this interconnect is determined by the memory clock, so the higher you go on memory clock, the better, although I saw some numbers that say you shouldn't go over DDR4 3600.
As 3600 MHz seems to be also the point after which price to performance drops rapidly, I decided to go with that.
CL16 is also nice, because this keeps latency low, CL14 would be better but this is again the spot for price to performance after which it becomes very expensive (and CL14 doesn't make that much of a difference).

GPU:
I didn't upgrade my GPU (as the only part which I kept besides the case) because it made no sense.
The cheapest upgrade that I could get would cost me about 700-800€ at current prices, giving me about 15% more power.
As I'm not gaming that much anymore (especially not the latest AAA titles) and considering that I bought my 1070 for 270€, its not worth the price :D

Fans:
I wanted this system to be as quiet as possible, as I was annoyed by my old system for many years.
Noctua Fans are not cheap, but holy.. the converters in my LED lamps are now louder than my system at idle (which it does for most of the day).
Oh, and I went for the ugly ones because they include more accessories (I specifically went for the extensions which I need for my case).