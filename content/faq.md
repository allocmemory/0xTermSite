+++
title = "FAQ"
description = "Questions about 0xTerm."
+++

### What does "drawn by the GPU" mean here?

The window is built with GPUI, the UI framework from Zed, which renders
through Metal. The terminal grid is painted as quads and shaped text runs
each frame, the way a game draws a scene. The logo on this page is drawn
the same way, by a shader on your GPU.

### Which Macs will it run on?

It is built and tested on Apple Silicon with the current macOS. The
minimum version will be set when v0.1 ships.

### Does it have AI features?

No, and none are planned.

### Does it do tmux or SSH integration?

Not in v0.1. Profiles, a settings window, triggers, scripting and
auto-update are also left out of the first release.

### What license is it under?

That is not decided yet. It will be in the repository before the first
release.

### Why the name?

`0x` is how a hex number begins, the prefix in front of every address and
color code a terminal shows you. The logo puts it at the prompt, where a shell's `$` would be.
