---
layout: post
title: "How to enable sound in VMware Player Guest OS"
date: 2012-07-30
---

Power off the guest VM.

Open up the .vmx file in the appropriate directory in your host OS to
edit it.

Make sure the following lines are in there. If not, add them.

sound.present = "TRUE"

sound.virtualDev = "es1371"
sound.filename = "-1"
sound.autodetect = "TRUE"

Credit goes to this post.