---
title: "My IRL Set Up"
date: 2020-12-28T15:26:08-05:00
draft: true
images:
tags:
  - irl
---



by [dawjanox][1]

_!! Amazon Affiliate Links !!_

### **Main Gear**

* Encoder: [UrayCoder][2]
* Cam: [GoPro Hero5][3]
* Power: [Halo Bolt][4]
* Mic: [Rode Video Micro][5]


### **Mounting Gear:**

* Mount: [Woods 6 inch vacuum cup mount][12]
* Arm: [SMALLRIG articulating arm][13]
* Ball Head: [Neewer Ball Head][14]


### Server/Software:

* NOALBS: [check it on github][18]
* SLS: [check it on gitlab][19]
* OBS-STUDIO: [check the OBS Project website][20]
* Linode: [Here is a referral link][21]


**Notes:** I plan on doing a full write up of this set up but this is my gear list for IRL right now. I use [H.265][22] to encode and send the feed over the [SRT][23] protocol - because [H.265][22] takes half the bitrate than typical [H.264][24] for the same video quality. Every major streaming platform uses only [RTMP][25] which does not support [H.265][22]. Using my mobile network I relay that feed to an [SLS][19] server on a [Linode][21] instance . I have [NOALBS][18] running on a [Debian10][26] [_Virtual Machine_] on my home PC which reads the active feed and changes scenes in [OBS][20] depending on my bit rate. My PC runs [OBS][20] which pulls the [SRT][23] feed from my [SLS][19] server on [Linode][21], then re-encodes to [X.264][27] and sends it to [Twitch][1] over [RTMP][25].

**12.09.20** 1st irl stream but using H.264 over [RTMP][25] which went to the noalbs server I set on my home stream PC (using the NGINX rtmp module) then rendered and encoded in OBS and sent to my twitch channel. This consumed quite a bit of data being that I was using h.264. I also used an OBS noise filter taht was way to aggressive in that people coming into my stream heard absolutley no backround or engine noise. So unless I was speaking they thought there was no audio in my stream.
[![TRKn8ntEZ! ::: ep.001](images/Trkn8ntEZ-ep001.jpg)](https://youtu.be/iPdmGJBOeak)
*TRKn8ntEZ! ::: ep.001 click to watch*

**12.26.20** Success! Well success in that I got h265 over srt as a workable proof of concept operation. My mobile carrier unfortunatley killed my bandwidth by throttling my tehering speed to 600kbps. Which made the stream pointless and unusable. I've had to use SLS server on my linode instance to bypass the firewall problems i've had with my [pfsense](http://www.pfsense.org) rouiter and SRT. I'm hoping to employ the powers of the Boy Wonder networking genius a.k.a. [fragpad](https://twitch.tv/fragpad)
[![TRKn8ntEZ! ::: ep.002](images/Trkn8ntEZ-ep002.jpg)](https://youtu.be/8IsaG5jjRik)
*click to watch*

**01.05.21**

[![TRKn8ntEZ! ::: ep.003](https://i9.ytimg.com/vi/giq4vNBcdfo/mq2.jpg?sqp=COzclIAG&rs=AOn4CLBeisXtQkpVsKhQPSqS6_XKTKtl4Q)](https://youtu.be/giq4vNBcdfo)
*click to watch*

**01.13.21**

[![TRKn8ntEZ! ::: ep.004](https://i9.ytimg.com/vi/e1fwMLoSAGA/mq2.jpg?sqp=CJjflIAG&rs=AOn4CLAffqTVkWQ-X1D_YTJnSn9BrPd5Sg)](https://youtu.be/e1fwMLoSAGA)
*click to watch*

An honorable mention to the [IRL Hub][28] discord community who helped me greatly with the install process. Others to be mentioned as well as I build this page out. Yours Truly [dawjanox][1]

[1]: https://www.twitch.tv/dawjanox
[2]: https://www.amazon.com/gp/product/B07DS47XF3/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07DS47XF3&linkCode=as2&tag=dawjanox-20&linkId=8392897d9968339ff04b75849ac7fd12
[3]: //ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B01MT0TJOM&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL110_&tag=dawjanox-20
[4]: //ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B07FM85W13&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL110_&tag=dawjanox-20
[5]: https://www.amazon.com/gp/product/B07KGJ9WDF/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B07KGJ9WDF&linkCode=as2&tag=dawjanox-20&linkId=1ada890eedcc050c5b8c0c1eef6132e5
[6]: //ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B07DS47XF3&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL110_&tag=dawjanox-20
[7]: //ir-na.amazon-adsystem.com/e/ir?t=dawjanox-20&l=am2&o=1&a=B07DS47XF3
[8]: //ir-na.amazon-adsystem.com/e/ir?t=dawjanox-20&l=am2&o=1&a=B01MT0TJOM
[9]: //ir-na.amazon-adsystem.com/e/ir?t=dawjanox-20&l=am2&o=1&a=B07FM85W13
[10]: //ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B07KGJ9WDF&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL110_&tag=dawjanox-20
[11]: //ir-na.amazon-adsystem.com/e/ir?t=dawjanox-20&l=am2&o=1&a=B07KGJ9WDF
[12]: //ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B00IDF1AC6&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL110_&tag=dawjanox-20
[13]: //ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B00NW6HDAE&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL110_&tag=dawjanox-20
[14]: //ws-na.amazon-adsystem.com/widgets/q?_encoding=UTF8&MarketPlace=US&ASIN=B071JWMS5J&ServiceVersion=20070822&ID=AsinImage&WS=1&Format=_SL110_&tag=dawjanox-20
[15]: //ir-na.amazon-adsystem.com/e/ir?t=dawjanox-20&l=am2&o=1&a=B00IDF1AC6
[16]: //ir-na.amazon-adsystem.com/e/ir?t=dawjanox-20&l=am2&o=1&a=B00NW6HDAE
[17]: //ir-na.amazon-adsystem.com/e/ir?t=dawjanox-20&l=am2&o=1&a=B071JWMS5J
[18]: https://github.com/715209/nginx-obs-automatic-low-bitrate-switching
[19]: https://gitlab.com/mattwb65/srt-live-server
[20]: https://obsproject.com
[21]: https://www.linode.com/?r=6a8aa6205c7810f18ddaf82aaa0098ec876d5899
[22]: https://en.wikipedia.org/wiki/High_Efficiency_Video_Coding
[23]: https://github.com/Haivision/srt
[24]: https://en.wikipedia.org/wiki/Advanced_Video_Coding
[25]: https://www.haivision.com/resources/streaming-video-definitions/real-time-messaging-protocol-rtmp/
[26]: https://www.debian.org
[27]: https://en.wikipedia.org/wiki/X264
[28]: http://https://discord.gg/kPgwxEg
