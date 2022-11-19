---
title: "H265 Over Srt Headaches"
date: 2020-12-14T16:31:22-05:00
draft: true
toc: false
images:
tags:
  - irl
---

So, you have an encoder that is capable of h.264 over SRT? You want to feed the video into OBS? Have you also found that h.265 over SRT is not as well documented as say h.264 over RTMP? I bet you have and so did I. I also banged my head against walls, keyboards, tables, innocent by-standards on the street,.. in all - ***I*** - was the biggest obstacle in the way of successfully achieving my 1st SRT transmission. This happens to me frequently when documentation is scarce or null. So I will describe the errors that kept me from successfully pushing SRT over IP.

***Mistakes***

- Don't use git clone with the sudo command
- Don't use Debian Buster, use Ubuntu Server stable.
- Get outside more, what are you doing?  

So firstly I ran this on a linode instance because at the time of writing I can't seem to get SRT through my pfsense firewall. But hosting this server externally doesn't seem to be any problem. This is not ideal however because it costs $5 per month not to mention my computer that runs OBS an home would be capable of running this server. This will do for the time being until I resolve the firewall issues.

***When Ubuntu is running do the following***
---

```bash
# update system
sudo apt update && apt upgrade -y
reboot

# install haivision srt
sudo apt install git tclsh pkg-config cmake libssl-dev libsrt-dev build-essential -y
git clone https://github.com/Haivision/srt.git
cd srt
./configure
make
sudo make install
```

---
***You should see this message***
---


```bash
#******************************************************************************#
#                          Build successful !                                  #
#******************************************************************************#
```

---
***Now install srt-live-server***
---


```bash
# install sls
cd ..
git clone https://gitlab.com/mattwb65/srt-live-server.git
sudo apt install lib32z1-dev -y
cd srt-live-server
make
cd bin
./sls -h
```

While searching for error solutions I stumbled on this post in which the library was not being copied over during the make install process.

[github haivision srt issue 103](https://github.com/Haivision/srt/issues/103)

A special thanks to the folks at the [IRL HUB](https://www.irlhub.net) discord server for their assistance in walking me through these errors!
