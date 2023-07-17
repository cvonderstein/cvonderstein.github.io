---
layout: default
title: Home-Server
has_children: true
nav_order: 5
permalink: hardware/home-server
parent: Hardware
---

# Home-Server

## The Hardware

- CPU: Ryzen 5 5600 (6x 3.6 GHz)
- Mainboard: Gigabyte B550 Aorus Elite V2
- RAM: 4x 16 GB DDR4-3200 Kingston Server Premier DIMM, Unbuffered ECC
- SSD: 2x WD Blue SN570 NVMe 1 TB, in Software (ZFS) RAID 1
- HDD: 2x 18 TB Toshiba Enterprise Capacity MG09ACA 512e SATA 6Gb/s, also in ZFS RAID 1
- PSU: 700W be quiet! System Power 7
- Case: Sharkoon VS4-V
- OS: Proxmox

## Some explanations

### CPU: Ryzen 5 5600

- Lots of power to host VMs
- ECC support (Note: the 5600G, i.e. the version with iGPU, does *not* have ECC Support)
- Still small, i.e. no extraordinary high power draw

### Mainboard: Gigabyte B550 Aorus Elite V2

- Many options
- Requirements
  - Compatible to Ryzen 5000
  - ECC Support
  - 2x M.2 with 4 lanes each (which has thrown out some cheaper boards, as they often only have the second slot x2), only noticed just before buying it
  - 4x DIMM
  - at least one CPU Fan header + at least two system fan headers
  - 4x SATA
- Not cheapest brand, which often save a buck on some features such as better power control

### RAM: 4x 16 GB DDR4-3200 Kingston Server Premier DIMM, Unbuffered ECC

- ECC
- 64 GB
- Unbuffered because Ryzen
- DDR4 >= 3200
- Otherwise I didn't really care

### SSD: 2x WD Blue SN570 NVMe 1 TB, in Software (ZFS) RAID 1

- wanted 2x (RAID 1) 1TB for OS, VMs and caches for HDDs
- Cheapest 1TB NVMe SSDs from reputable brand
- no bad reviews on the internet (besides some "its not the fastest SSD, only the cache is fast")
- notice: these SSDs use a fast cache (the 3GB/s or whatever they advertise), storage after that is slower, these ones are particularly slow with only about 500MB/s, but I didn't care as this is not the workload I expect them to do

### HDD: 2x 18 TB Toshiba Enterprise Capacity MG09ACA 512e SATA 6Gb/s, also in ZFS RAID 1

- Price per TB
- Thinking 14TB+
- Use Helium filled ones due to lower power consumption (12? TB and higher) -> also link data sheet
- Good experience with Toshiba at work
- Toshiba has good prices
- Bought on sale
- Again: Two in RAID 1 just to be safe
- Usage: Data, mostly as backup from other machines, but also backups of VMs

### PSU: 700W be quiet! System Power 7

Just what I currently had unused.
I tested a beQuiet 300W 80 Plus Bronze (which is basically the smallest PSU I was able to find), but it only saves about 2W constant power draw, so that would be an investment that only returns after like 8 years.
I also tried a picoPSU, which not only doesn't give me enough SATA Ports, but also only saves about 4W compared to the 700W PSU, but since it also costs about twice as much as the 300W beQuiet one (you also need something like a beefy Laptop Power Brick as the picoPSU requires a 12V input), this "investment" also returns only after about 8 years.

Therefore I went with the old 700W one, which I'm going to replace as soon as the old one gives up.

> But why do you even compare a 700W 80+ Silver to a 300W 80+ Bronze?

Well, the 80+ Specs only define a required efficiency for certain amounts of load, starting at 20% load of the PSU.
Okay, 80+ Titanium also requires a certain efficiency at 10% load, but these PSUs already so expensive that this doesn't make sense from a financial view in the first place.
But since the whole System uses below 40W idle, and with HDDs and some VMs running maybe about 60W, the 700W PSU sits even below 10% load, at which it can have basically any efficiency and still meet the certification.
My hope was that the 300W PSU is a lot more efficient since its sitting at about 20% load, but this wasn't the case.

### OS

- User friendly
- Its still Linux
