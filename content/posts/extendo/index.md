---
date: "2025-08-05T08:38:14+01:00"
draft: false
title: "Extensions"
layout: "background"
---
As part of the block picking work I had to move the Input Context which handles in game actions from
the main framework into the extension.  So I figured it's probably worth a quick explanation of how
extensions currently work.

{{< alert >}}
This is almost certainly going to radically change...
{{< /alert >}}

The rise framework will scan the local `extensions` folder and then search for `dll` files within
subfolders. Each subfolder will be treated as it's own extension. The `dll` file will then be
searched for any public class which inherits from `Extension`. All libraries with the extension
folder will then be searched for event handlers. The list of event handlers is currently things
like:
- `TickEvent`
- `Local/NetworkClientConnectedEvent`
- etc.

The next step is to invoke `AddServices` on the extension instance. This will give the extension a
chance to register or override any services in the DI container. (Due to security there will
probably only be a handful of well defined extension points that are allowed to be overridden, but
for now it's everything.)

Once the extension class and event handlers are loaded the `OnEnabled` method of the extension
instance is invoked. Allowing the extension to perform any initialisation it needs. The `OnEnabled`
method will receive an instance of the extension `IHost` which will provide access to framework
services.

What all this means is that the entire voxel game is an extension. And I will provide additional
extensions which showcase what can be achieved and possibly even make them open source.

I'll demonstrate all this in more depth soon.

