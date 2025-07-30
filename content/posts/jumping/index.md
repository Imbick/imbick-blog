---
date: "2025-07-30T17:52:02+01:00"
draft: false
title: "Jumps"
layout: "background"
---
Far less progress made this evening.  
A major refactor on the way input contexts work.
So now all of the physics code for deciding what happens when a player jumps or collides etc is
controlled by the input context which is a more sensible place for it to live.

In doing so I started to notice how poor the physics code was implemented, so I restructured a lot of that.
Which enabled me to model the jump physics more accurately - so no more jetpacks :'(

Tomorrow I hope to work more on the jump handling and general movement of the player so things feel more natural.

Then I'll probably turn my attention to interaction with the world, which should make this thing start to become more like a real ~boy~ game.