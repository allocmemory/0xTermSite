+++
title = "0xTerm"
+++

## What is 0xTerm?

0xTerm is a minimal terminal for the Mac, drawn by the GPU, with file
search and a file viewer built in. It is written from scratch in Rust.

I live in the terminal, and I used iTerm2 for years. I wanted something
smaller: a quiet window drawn by the GPU, and a way to find files and read
them without leaving it. cmux, Warp and Wave do that, along with much more
than I need. So I made 0xTerm.

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
dotfiles. The [docs](@/docs.md) list the shortcuts
and the config file, and the [FAQ](@/faq.md) answers the obvious questions.
Got a problem or an idea? Email me at
[allocx@mailbox.org](mailto:allocx@mailbox.org).

## Download

<p class="status">There is no build yet. 0xTerm is in development, working
toward v0.1.</p>

The [downloads page](@/downloads.md) says what v0.1 will ship as and how to
follow along.

## Donate

0xTerm is free and built in my own time. If it's useful to you, you can
back it on Patreon for $1, $2.50 or $5 a month, or any amount you choose.

<p><a href="https://www.patreon.com/c/Allocmemory">Donate on Patreon<svg class="ico" viewBox="0 0 16 16" aria-hidden="true"><path d="M8 14.5 1.9 8.6A3.9 3.9 0 0 1 7.4 3.1L8 3.7l.6-.6a3.9 3.9 0 0 1 5.5 5.5Z"/></svg></a></p>
