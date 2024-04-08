---
layout: post
title:  "2023.1-beta6: New App, PineTab2, and more!"
date:   2023-06-30 00:00:00 +0100
author: ajstrongdev
---

This beta release brings a flurry of desktop improvements, bug fixes, and under-the-hood improvements to the distribution, as well as a new platform to run Rhino Linux on! Our biggest changes are:

# Your System

* The inclusion of our new Your System app, a handy graphical application that allows for you to view system information at a glance. Furthermore, it provides a graphical method for you to update all of your software packages.

# PineTab2

* Joining Rhino Linux's mobile & Pine64 ecosystem is the newly released PineTab2! Our images comes with the bootloader pre-installed, so you can flash it directly to your preferred storage volume and get going. The port uses kernel 6.3.9-rockchip from the Mobian team, and has auto-rotation, audio, USB networking, and more working out-of-the-box. Combining this with our minimally-patched Unicorn Desktop environment unicorn-mobile-git, Rhino Linux provides a perfect and stable experience for you to get started experimenting with your new Linux tablet. (NOTE: the WiFi driver for the PineTab2 has not been ported yet. See https://wiki.pine64.org/wiki/PineTab2#How-to for current solutions.)

# RhinoDrop
* Enhance your productivity with RhinoDrop. RhinoDrop allows for you to effortlessly send files across devices connected to your local network. RhinoDrop stores no images sent through its platform, and operates on a peer-to-peer connection with encrypted transit so you can rest assured your data is safe. Visit https://drop.rhinolinux.org to use now.

# As well as...
* Pacstall 3.15.0 has released, featuring a vital component that will assist Rhino users: a dependency tree! This assists the upgrade process with ordering, so that your package's dependencies are installed in the correct order. For packages like linux-kernel and linux-kernel-stable this is especially important, so be sure to upgrade to the latest version! See below for how.

* Unicorn has seen some improvements and changes, such as the disabling of animations on xfdashboard and rearranging our panel. This is now pre-packaged in the latest ISO file and core pacscripts.

* When you open up Firefox, you will now be greeted with https://rhinolinux.org/landing, which will give you quick-links to our Wiki, News, Contact and RhinoDrop. Users on 2023.1-beta5 and below will not recieve this change, and will need to run this command to recieve the change:

{% highlight bash %}
sudo rm -r /etc/firefox/syspref.js
echo 'pref("browser.startup.homepage", "https://rhinolinux.org/landing/");' | sudo tee -a /etc/firefox/syspref.js
{% endhighlight %}

If you are on a previous release, you can update your system to install the rest of the latest changes with:

{% highlight bash %}
pacstall -U pacstall:master
rpk update -y
{% endhighlight %}
