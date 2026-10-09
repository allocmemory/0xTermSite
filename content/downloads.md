+++
title = "Downloads"
description = "Download 0xTerm for macOS."
template = "downloads.html"
+++

### Install

Open the DMG and drag 0xTerm to Applications.

### First launch

Releases aren't notarized by Apple yet, so macOS blocks the first launch.
Do one of these:

- Open 0xTerm once and dismiss the warning. Then go to **System Settings →
  Privacy & Security**, scroll down, and click **Open Anyway** next to
  0xTerm.
- Or, in a terminal:
  `xattr -dr com.apple.quarantine /Applications/0xTerm.app`

After that it opens like any other app.

### Check the download

```sh
shasum -a 256 ~/Downloads/0xTerm-0.1.0.dmg
```

The output should match the SHA-256 above.

### Known issues in 0.1.0

- Expanding Desktop, Documents or Downloads in the file tree shows the
  macOS privacy prompt, and the window waits until you answer it.
- Emoji are drawn slightly wider than two cells.
- Wide Mermaid diagrams shrink to the viewer's width.

### Build from source

You need current stable Rust and Xcode. The Command Line Tools alone aren't
enough, because GPUI compiles its Metal shaders at build time.

```sh
git clone https://github.com/allocmemory/0xTerm
cd 0xTerm
cargo run -p oxterm        # run a debug build
packaging/install.sh       # build and install to /Applications
```

### Support it

If 0xTerm is useful to you, you can back it on Patreon.

<p><a href="https://www.patreon.com/c/Allocmemory">Donate on Patreon<svg class="ico" viewBox="0 0 16 16" aria-hidden="true"><path d="M8 14.5 1.9 8.6A3.9 3.9 0 0 1 7.4 3.1L8 3.7l.6-.6a3.9 3.9 0 0 1 5.5 5.5Z"/></svg></a></p>
