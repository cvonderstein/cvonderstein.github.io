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
- OS: Windows 10 Education (similar to Pro)

## Some explanations

### CPU

My [old system](Home-Server.md) has an Intel Core i7-5820k (6 cores overclocked to 4.2 GHz), so I needed something bigger for an upgrade, going from six to 8 cores was in my opinion not worth it.
As price/performance is relatively stable across the different Ryzen Processors, I went with a 12-core processor, giving me twice as many cores and about twice as much performance per core, which is nice.
I think I never really maxed this processor out, besides some benchmarking and playing around how much I can crank up OBS settings and similar stuff.
So I'm pretty happy with it, besides the temperatures which are quite a bit higher than what I was used to from my i7-5820k before.

I think one or two days after I ordered the system (I had not even received it), the new Intel processors were launched, but I'm very happy that I went with this system.
I was already an early adopter with DDR4 at the end of 2015, which didn't pay off as this new technology costs a lot of money just after release, but the performance benefit is not really there yet.

### SSDs

Yes, I have 4 TB of SSD Storage.
Why? Part of that is because I initially planned to get 3 TB, just to have enough storage and to have a NVME Gen 4 for my OS, a NVME (Gen 3 because the Chipset on the Mainboard doesn't offer a second Gen 4 slot) for VMs and stuff and a SATA SSD for games (they don't really profit from faster NVME drives, LinusTechTips tested it in a video).
I also didn't want spinning disks because of the noise (currently the power converters in my lamps are louder than my whole PC at idle..).

As the two NVME Drives, I got the 980 Pro and the 970 Evo, as these are the best options: The 980 Pro is currently the fastest (consumer) NVME SSD, and the 970 Evo is the fastest PCIE Gen 3 one (faster than the normal 980 and also faster than the 970 Pro).
For the SATA SSD, I ordered the MX500 which was a little cheaper than the 870 EVO (although its slightly slower on paper).
A few days later, the price of the 870 EVO dropped because of black friday, and as it is a bit faster I also ordered this one.
I planned on returning the MX500, but as I had already written like half a terabyte on that drive, I decided to be nice to other people and keep it.
And another Terabyte of SSD Storage never hurts :D

### RAM

First, a bit of background:
The larger Ryzen processors have two partitions on one chip (called chiplets), which are connected using what AMD calls "infinity fabric".
The clock frequency of this interconnect is determined by the memory clock, so the higher you go on memory clock, the better, although I saw some numbers that say you shouldn't go over DDR4 3600.
It is technically possible to use two different clock speeds for RAM and the infinity fabric, but comparisons observed large performance drops when you do this.

As 3600 MHz seems to be also the point after which price to performance drops rapidly, I decided to go with that.
CL16 is also nice, because this keeps latency low, CL14 would be better but this is again the spot for price to performance after which it becomes very expensive (and CL14 doesn't make that much of a difference, comparisons I saw showed about 1%).

### GPU

I didn't upgrade my GPU as the only part which I kept besides the case because it made no sense.
The cheapest upgrade that I could get would cost me about 700-800€ at current prices, giving me about 15% more performance.
As I'm not gaming that much anymore (especially not the latest AAA titles) and considering that I bought my 1070 for 270€, its not worth the price :D

### Fans

I wanted this system to be as quiet as possible, as I was annoyed by my old system for many years.
Noctua Fans are not cheap, but holy are they quiet.. the converters in my LED lamps are now louder than my whole system at idle (which it does for most of the day).
Oh, and I went for the ugly ones because they include more accessories (I specifically went for the extensions which I need for my case).
As I don't have any RGB (okay, my mainboard has some but I didn't even bother turning it off or whatever, I just don't care about this) inside my system, I don't really see them anyways.

### OS

I don't use Linux, because of gaming.
Even though Windows sucks (often), gaming on linux is a real pain as [Linus Tech Tips tested in a whole video series](https://youtube.com/playlist?list=PL8mG-RkN2uTyhe6fxWpnsHv53Y1I-K3yu).
Dual-boot is not an option, because I really do not want to close all applications and reboot my computer just to fire up a game for a few minutes.
If I need Linux (or if it helps at least, e.g. with [LaTeX](../Software/LaTeX.md)), I simply use VMs.
