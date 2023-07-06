---
title: "Setting Up Static IP in Fedora 19"
date: 2014-01-06T13:10:30+05:30
categories:
  - blog
tags:
  - linux
  - tech
---

Setting up internet on Linux environments can be tough !  Many Linux enthusiasts return to Windows due to this . This post will help you in setting up static IP in fedora if you are unable to do so via the GUI Network Manager.

If the settings in your Network Manager (GUI) are greyed out (as in my VM environment) you can use the console way to set up static IP by following this guide !

Disclaimer : Please backup your files before proceeding !

- Open up a terminal .

- Find out your desired  interface using 

```
  root@x (~):ifconfig
```

  Edit the config file for that interface using vi editor
  
```  
  root@x (~):vi /etc/sysconfig/network-scripts/ifcfg-eth0  //where eth0 is the desired interface
```

  PS. this is a read-me file , so allow to change when asked.

- Ensure that the configuration file looks simular to the following:

```
  TYPE=Ethernet
  BOOTPROTO=dhcp
  DEVICE=eth0
  ONBOOT=yes
```

- You will need to change BOOTPROTO from dhcp to static and add IPADDR, NETMASK, BROADCAST and NETWORK variables.

```
  BOOTPROTO=static
  DEVICE=eth0
  ONBOOT=yes
  IPADDR=192.168.8.248
  NETMASK=255.255.255.0
  BROADCAST=192.168.8.255
  NETWORK=192.168.8.0
  GATEWAY=192.168.8.1
  TYPE=Ethernet
```

- Save the settings by pressing Esc in vi editor and typing

```
  :w !sudo tee % > /dev/null
```

- Also , add your DNS servers (if you use custom DNS)

```
  root@x (~): vi /etc/resolv.conf
  nameserver your_Router_ip
  nameserver 8.8.8.8
``` 

All Done, Go Surf!