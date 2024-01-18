---
cvs: "$Id: my-home-vps-test-lab.md,v 1.3 2024/01/11 18:12:48 mcornick Exp $"
author: Mark Cornick
date: 2021-01-23
title: My Home VPS Test Lab
---
I learn by doing; always have. If I want to learn how something is done, the most effective way for me is not to read about it, or to listen to someone talk about it, but to get my hands dirty doing it. It's true for so many things I've learned, but especially my trade of UNIX system administration. Ever since I first got root on a UNIX system (my first Slackware installation way back in 1994) it's been this way. Sure, I've looked at the man pages from time to time, and read a tutorial or two, but mostly, it's just been a matter of, to use old BASIC terminology, poking and peeking and seeing where it gets me.

Over the past several years, that experimentation has often taken place on VPS instances I've rented from various providers. For \$5/month, you can have a VPS with about a gigabyte of ram, one CPU, and a big enough disk to install the OS and a bunch of packages, from any of a number of providers. This makes the cost of entry for experimental instances pretty low, and I've had great success trying things this way.

And yet, I was ignoring a resource available to me essentially for free (in that I've already paid for it): a PC under my desk that I used to use for gaming. I put Debian on it several months ago, and it works great, but I wasn't using it to its full potential. My daily driver these days is a MacBook Air, so the PC was mostly sitting there.

And then one day I heard about [Proxmox Virtual Environment](https://www.proxmox.com/en/proxmox-ve), a customized Debian distribution which provides a solid UI around the QEMU/KVM hypervisor system. From its web UI, you can create and monitor virtual machines running all kinds of operating systems. While there are paid subscriptions available, Proxmox is perfectly usable without one.

The machine has 12 Intel i7-8700 cores, 32 GB of RAM, and 2 TB of disk (not including the NVMe boot disk.) That's plenty of horsepower to run a bunch of instances comparable to the VPSes I mentioned above. In the end, I settled on 12 VMs with 1 CPU, 2 GB of RAM, and 32 GB of disk each, with the following operating systems:

* Alpine Linux 3.13.0
* Arch Linux
* CentOS Stream 8.3
* Debian 10.7
* Fedora 33
* FreeBSD 12.2-RELEASE
* NetBSD 9.1
* NixOS 20.09
* OmniOS CE r151036
* OpenBSD 6.8
* openSUSE Leap 15.2
* Ubuntu 20.04

That's 12 systems, running the gamut from Linux to BSD to Solaris, all at my fingertips whenever I'm at home (which, let's be fair, is pretty much all the time under current conditions), all for essentially nothing (given that the hardware is already paid for.) And I've got plenty of room to try other things if I want.

If you've got a spare PC at home and want to explore the world of open-source virtualization, give Proxmox a try! It's powerful yet very approachable, and you can have a home VPS test lab like mine in no time.
