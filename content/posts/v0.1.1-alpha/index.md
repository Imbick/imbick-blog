---
date: "2025-08-12T17:38:45+01:00"
draft: false
title: "Release v0.1.1-alpha"
layout: "background"
---
It's been a while without any updates here, but here's the latest version packaged up.

{{< button href="/downloads/rise-0.1.1-alpha.zip" target="_self" >}}
{{< icon "download" >}}
&nbsp;Download v0.1.1-alpha
{{< /button >}}

I've been massively overhauling the way input contexts work along with the  physics calculations. I
took a detour into experimenting with [EnttSharp](https://github.com/RabbitStewDio/EnTTSharp), but
it ended using over 25% CPU whenever components were written back which seemed excessive so I
rolled back to [LeoEcsLite](https://github.com/LeoECSCommunity/ecslite) but kept some of the API
refactoring which was an improvement.

Next I'll be continuing to tweak the physics numbers to get a good feeling. Along with fixing the
jump code and wall slide accelerations which shouldn't be happening.