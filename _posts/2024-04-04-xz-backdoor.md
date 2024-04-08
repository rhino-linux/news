---
layout: post
title:  "Important information regarding xz backdoor"
date:   2024-04-04 00:00:00 +0100
author: ajstrongdev
---

We know many of you are tired of hearing about the xz backdoor, but we must share important information regarding it. After doing some digging, we confirmed that from Feb 16 to Mar 28 (both of this year), the affected packages were in Ubuntu's noble/devel repositories, directly impacting Rhino Linux. This only affected x86_64/amd64 deployments, aarch64/arm64 was not impacted. (<https://discourse.ubuntu.com/t/xz-liblzma-security-update/43714>)

The package has been removed from their repos now, and it is imperative that you ensure you have updated your xz-utils. To do so, please run the following command (DO NOT use rpk update for this - more explained below):

`sudo apt update && sudo apt install --reinstall xz-utils -y`.

Additionally, it is also a safe and recommended idea to update your ssh keys after updating the package.

As mentioned above and in other important announcements, running rpk update/sudo apt upgrade is currently (for the next week or two) a risky move. Debian and Ubuntu are in the peak of transitioning to 64-bit time, which comes at the cost of them rebuilding virtually every package. (<https://wiki.debian.org/ReleaseGoals/64bit-time>)

This is causing issues, as some t64 dependencies of other t64 packages are not ready before their parents, which could result in possible system breakage if it is just the wrong packages. This breakage extends all the way to debootstrap being stuck, meaning we cannot even generate test .ISO images for development. (<https://wiki.debian.org/BrainDumpT64>)

We will be providing updates as the dependency issues are resolved. Thanks for sticking around and let us know if you need help or have any questions. Cheers and happy developing,

The Rhino Linux Team
