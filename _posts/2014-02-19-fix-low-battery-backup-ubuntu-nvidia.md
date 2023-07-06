---
title: "Fix low battery backup on Ubuntu with nVidia GPU"
date: 2014-02-19T13:10:30+05:30
categories:
  - blog
tags:
  - linux
  - tech
---

If you are using Ubuntu on a laptop with nVidia Graphic card you must have faced the problem of low power backup. Your laptop might be running with power backup of 4 hours with Windows, but when using UBUNTU it may not even give backup of 2 hours.

So what’s the problem and how to tackle this problem ??

Usually Windows switches between integrated intel graphics and the dedicated nVidia graphics processor to save battery but Ubuntu natively doesn't provide this support.

So the solution is a third party utlity - Bumblebee. Bumblebee provide support for systems with NVidia graphic card and helps switch graphics processor as per need. The idea is that graphics intense programs will only use the heavier NVidia card when needed – the rest of the time the Intel card will be used. This is intended to conserve resources and hence increase battery backup. This could be done simply by installing Bumblebee which can automatically do the switching.

# Installation

You need to open your terminal and enter the commands below

For UBUNTU 13.04 and  previous versions

```
sudo add-apt-repository ppa:bumblebee/stable
sudo apt-get update
sudo apt-get install bumblebee bumblebee-nvidia virtualgllinux-headers-generic
```

For UBUNTU 13.10 and later

```
sudo apt-get install bumblebee bumblebee-nvidia primus linux-headers-generic
```

Reboot your system and you are good to go. Now enjoy using your laptop with much better battery backup!

 