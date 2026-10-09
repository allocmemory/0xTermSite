+++
title = "Docs"
description = "0xTerm shortcuts, config file and architecture."
+++

### Shortcuts

| Keys | Action |
|---|---|
| ⌘T / ⌘W | new tab / close pane |
| ⇧⌘[ / ⇧⌘] | previous / next tab |
| ⌘D / ⇧⌘D | split right / split down |
| ⌘[ / ⌘] | previous / next pane |
| ⌘B | show or hide the file tree |
| ⇧⌘B | show or hide the viewer |
| ⌘F | find in the open file |
| ⇧⌘F | search the folder |
| ⌘K | clear the terminal |
| ⌘-click | open a `path:line` or a URL |

### Config

0xTerm reads `~/.config/0xterm/config.toml`. Every key is optional, and
anything you leave out keeps the value shown here.

```toml
[font]
family = "Menlo"
size = 13.0
line_height = 1.2

[terminal]
shell = ""            # empty means your login shell ($SHELL)
scrollback = 10000
option_as_meta = true # ⌥+key sends ESC+key, for word movement

[theme]
mode = "system"       # or "light" / "dark"

[theme.dark]
background = "#0b0b0b"
foreground = "#e6e6e6"
```

`[theme.light]` takes the same keys. Each palette also takes `cursor`,
`selection` and a 16-color `ansi` list.

### How it is built

Bytes travel one way from the shell to the screen, and keys travel back:

```
zsh ⇄ pty ⇄ task (forkpty, reader thread)
              → alacritty_terminal (parser, grid, scrollback)
              → terminal view (GPUI on Metal, one snapshot per frame)
```

The window holds tabs, each tab holds a tree of splits, and each split ends
in a pane running a shell. Beside them sits the toolbelt: the file tree,
folder search and the viewer. The toolbelt talks to the panes only through
events, such as "open this file at this line" or "the working folder
changed".

| Crate | What it does |
|---|---|
| `oxt-task` | pty, child process, reader and writer threads, cwd and foreground job |
| `oxt-session` | terminal state, key, paste and mouse encoding, OSC 7 |
| `oxt-terminal-view` | draws the grid, selection, links, find |
| `oxt-window` | tabs, splits, panes |
| `oxt-toolbelt` | file tree, search, viewer |
| `oxt-config` | config file, themes, keymap |
