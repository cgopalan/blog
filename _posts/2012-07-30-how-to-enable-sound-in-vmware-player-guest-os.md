---
layout: post
title: "How to enable sound in VMware Player Guest OS"
date: 2012-07-30
---

Power off the guest VM.

Open up the .vmx file in the appropriate directory in your host OS to
edit it.

Make sure the following lines are in there. If not, add them.

sound.present = &quot;TRUE&quot;

sound.virtualDev = &quot;es1371&quot;
sound.filename = &quot;-1&quot;
sound.autodetect = &quot;TRUE&quot;

Credit goes to this post.