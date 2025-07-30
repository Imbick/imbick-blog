---
date: "2025-07-30T08:16:22+01:00"
draft: false
title: "Playing and fixing"
layout: "background"
---
Mainly fixing bugs this morning and getting things into a better state.  

There was a bug where the player would appear to accelerate towards the left or right when 'jumping'.
(Jumping currently behaves like some kind of crazy jetpack 👨‍🚀 - it very much shouldn't)  

This was due to me clamping each axis separately to within the max speed limits.
```csharp
x = float.Clamp(x, -MaxHorizontalSpeed, MaxHorizontalSpeed);
z = float.Clamp(z, -MaxHorizontalSpeed, MaxHorizontalSpeed);
```
This had the effect of keeping one axis below the speed limit, but allowing the other to continue
to accelerate.
Now I validate against the length of the vector rather than the individual axes.

As you can see from the screenshot I'm also now playing around with some different block
arrangements to try and find any weird edge cases with the collision detection.

I think I need to add a small offset when resolving intersections to avoid collisions with block
seams but need to find a reproducible test case first.
