+++
title = "0xTerm"
+++

## What is 0xTerm?

0xTerm is a minimal terminal for the Mac, drawn by the GPU, with file
search and a file viewer built in. It is written from scratch in Rust, and
every frame is drawn through Metal.

I live in the terminal, and I used iTerm2 for years. I wanted something
smaller: a quiet window drawn by the GPU, and a way to find files and read
them without leaving it. cmux, Warp and Wave do that, along with much more
than I need. So I made 0xTerm.

<img class="shot" src="/screenshot.png" width="1240" height="800" alt="0xTerm with the file tree on the left, a shell showing grep output in the middle, and the file viewer on the right open at a find match.">

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

Open it and type. Your login shell starts with your own `PATH` and
dotfiles, even when you launch from the Dock. The [docs](@/docs.md) list
the shortcuts and the config file, and the [FAQ](@/faq.md) answers the
obvious questions. Found a bug? Open an
[issue](https://github.com/allocmemory/0xTerm/issues), or email me at
[allocx@mailbox.org](mailto:allocx@mailbox.org).
