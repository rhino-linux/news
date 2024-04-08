---
layout: post
title:  "Open Beta, PinePhone (Pro) & more!"
date:   2023-07-26 10:48:00 +0100
author: ajstrongdev
---

Rhino Linux is pleased to announce that it has entered open beta. This is the collective work of 5 months of active development from the Rhino Linux team and other contributors. During the open beta please feel free to report any bugs by contacting us. Any known bugs will appear on the Rhino Linux wiki. For the next few weeks following this we will be following up with bug fixes and other beta disk images.

You can download the Rhino Linux Beta disk images from our Download page. Please do keep in mind that it is Beta software and so bugs and issues are to be expected. Please report them so that we can fix them before release.

# Pinephone Port

Hey all, oklopfer here! While we have been stabilizing the desktop version of Rhino Linux for beta release, I’ve also been working on a side project: Rhino Linux Mobile!

One of my other recent linux projects has been porting the latest version of Ubuntu Touch (20.04) to the PinePhone and PinePhone Pro, and I’ve brought that experience over to the Rhino team! With Rhino Linux mobile, I have created the first XFCE-based mobile environment. Originally, we were going to utilise Phosh as a desktop environment, however when investigating we quickly found that the Ubuntu repositories utilised to create Rhino Linux currently ship a broken Phosh package, so we came up with an alternative. Turns out, almost all of the mobile environments aren’t working on Ubuntu right now, so we fell back to what we knew worked soundly: XFCE. To do this, the environment utilizes onboard as the system keyboard, a slightly modified version of the Rhino Linux XFCE dotfiles, and a special patch for XFCE to allow for auto-rotation. It currently uses X11, but we are looking into moving to Wayland when XFCE 4.20 comes around.

The port itself was quite a simple process - we build a tarball of the filesystem in the live-build runner, then deploy the filesystem to a partitioned image and add the kernel files for the specified device in debos, and it’s good to go! You can see a video demoing the full environment here:

[![Rhino Touch Demo](https://img.youtube.com/vi/-qwja52J53s/0.jpg)](https://www.youtube.com/watch?v=-qwja52J53s)

# Quality of life + UX

While our original aim was to create a distro for the advanced linux user + developers, we also felt we should target newcomers. Linux today still relies too heavily on the terminal, and we would like to change that. That is why we are going to be creating graphical applications for rhino-pkg, Proprietary WiFi driver installation & updating your system.

![Rhino Linux System Mockup]({{ site.baseurl }}/assets/imgs/rhino-system-mockup.png)

Above is a mockup image of one upcoming application, code-named rhino-system, It will display system information, perform package upgrades graphically and handle WiFi driver installation (not shown). By creating these applications we hope to provide people an easier method of operating with their computers. Terminal applications still can be utilised for those who want them, though.
