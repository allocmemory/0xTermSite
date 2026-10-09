+++
title = "0xTerm"
+++

## What is 0xTerm?

0xTerm is a terminal for the Mac. It keeps the quiet, minimal window that
made iTerm2 worth living in, and adds the three things you leave the
terminal for most: a file tree, a file viewer and a Markdown preview.

It is written in Rust and drawn by the GPU. Every cell, glyph and cursor is
painted through Metal, and output is parsed off the main thread, so a
flood of output should never stall the window.

## Why do I want it?

Because you `cd` somewhere and then open Finder to see what is there. Or you
`grep` and then copy a path into an editor to read one line. 0xTerm keeps
those inside the window:

- The file tree follows your shell. `cd` and it moves with you.
- ⌘-click a `path:line` in any output and the file opens at that line.
- Markdown renders beside the shell, Mermaid diagrams included, and updates
  as you save.
- Drag a file from the tree onto the terminal and its path is typed for you.

No account, no AI, no cloud. A shell, the files it is looking at, and
nothing else. See the [features](@/features.md).

## How do I use it?

Open it and type. Your login shell starts as it does in Terminal or iTerm2,
with your own `PATH` and dotfiles. The [docs](@/docs.md) list the shortcuts
and the config file, and the [FAQ](@/faq.md) answers the obvious questions.

## Download

<p class="status">There is no build yet. 0xTerm is in development, working
toward v0.1.</p>

The [downloads page](@/downloads.md) says what v0.1 will ship as and how to
follow along.
