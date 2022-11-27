---
layout: default
title: Davinci Resolve HEVC/H.265
has_children: false
permalink: software/davinci-resolve-h265
parent: Software
---

# Davinci Resolve HEVC/H.265

> TLDR: Use Solution 1 if possible, otherwise Solution 2.

Problem: DaVinci Resolve says "Media Offline" for HEVC/H.265 Content.

Crappy possible solution you do not want to use: Use some kind of conversion software such as Handbrake to convert your media beforehand.
You don't want to use this because of three reasons:

1. Takes up a lot of space, at least temporarily, as you need to store your original file + your converted file during this conversion process. Also, every drive is somewhere limited in Writes until it breaks, and although they can usually do a lot and a normal user won't reach the limit, multiplying all your writes isn't the best idea, if there are better ways (and there are).
2. Lost quality. These codecs are not lossless (at least not in any senseful setting), and with lossless settings your files are just insanely huge. In the end, you will always lose at least some detail, even if its not much.
3. Its ugly and takes a lot of time. This is just not the intended way and there must be a better solution.

Use one of these solutions instead:

- Solution 1: Microsoft HEVC OEM Pack from [https://apps.microsoft.com/store/detail/hevc-video-extensions-from-device-manufacturer/9N4WGH0Z6VHQ](https://apps.microsoft.com/store/detail/hevc-video-extensions-from-device-manufacturer/9N4WGH0Z6VHQ).
- Solution 2: Pay $1 for Microsofts HEVC Extension from [https://apps.microsoft.com/store/detail/hevc-video-extensions/9NMZLZ57R3T7](https://apps.microsoft.com/store/detail/hevc-video-extensions/9NMZLZ57R3T7). Not sure where the difference to Solution 1 is, but as long as solution 1 works for you, use this instead. I was able to install the OEM Pack on my selfbuilt non-OEM Machine, so this shouldn't be the difference. But your mileage may vary.
- Solution 3: (not tested by me but should work anyways) [K-Lite Codec Pack](https://en.wikipedia.org/wiki/K-Lite_Codec_Pack). This pack brings a lot of codecs with it (not only H.265). I intentionally linked the Wikipedia aritcle here since Wikipedia also links to the original website, and I expect Wikipedia to stay better up-to-date than my site. The codecs should enable you to edit H.265 Material using DaVinci Resolve.

I got this solution from here: [https://www.youtube.com/watch?v=BhqPd8bWdOY](https://www.youtube.com/watch?v=BhqPd8bWdOY).
Give this guy a like and maybe a nice comment if this helped you.
