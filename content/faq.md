+++
title = "FAQ"
description = "Questions about 0xTerm."
+++

### Which Macs does it run on?

Macs with Apple Silicon, running macOS 13 or later. It is built and tested
on the current macOS.

### Why does macOS block the first launch?

Releases are signed, but not notarized by Apple yet. Open 0xTerm once, then
click **Open Anyway** in **System Settings → Privacy & Security**. The
[downloads page](@/downloads.md) has the details.

### What does "drawn by the GPU" mean here?

The window is built with GPUI, the UI framework from Zed, which renders
through Metal. The terminal grid is painted as quads and shaped text runs
each frame, the way a game draws a scene. The logo on this page is drawn
the same way, by a shader on your GPU.

### Does it have AI features?

No, and none are planned.

### Does it do tmux or SSH integration?

Not in v0.1. Profiles, a settings window, triggers, scripting and
auto-update are also left out of the first release.

### Does it update itself?

Not yet. Watch the [releases](https://github.com/allocmemory/0xTerm/releases)
on GitHub, then download the new DMG and replace the app.

### What license is it under?

The [GNU General Public License v3.0](https://github.com/allocmemory/0xTerm/blob/main/LICENSE).
The source is on [GitHub](https://github.com/allocmemory/0xTerm).

### Where do I report a bug?

In the [issues](https://github.com/allocmemory/0xTerm/issues), or by email
at [allocx@mailbox.org](mailto:allocx@mailbox.org). Security problems go
through [SECURITY.md](https://github.com/allocmemory/0xTerm/blob/main/SECURITY.md).

### Why the name?

`0x` is how a hex number begins, the prefix in front of every address and
color code a terminal shows you. The logo puts it at the prompt, where a
shell's `$` would be.
