+++
title = "Docs"
description = "0xTerm shortcuts, config file and architecture."
+++

### Shortcuts

| Keys | Action |
|---|---|
| ⌘T | new tab |
| ⌘N | new window |
| ⌘W / ⇧⌘W | close pane / close tab |
| ⌘D / ⇧⌘D | split right / split down |
| ⌘[ / ⌘] | previous / next pane |
| ⇧⌘[ / ⇧⌘], ⌃⇥ / ⌃⇧⇥ | previous / next tab |
| ⌘B | show or hide the sidebar |
| ⇧⌘B | show or hide the viewer |
| ⇧⌘F | search the folder |
| ⌘F | find in the open file |
| ⌘K | clear the terminal |
| ⌘C / ⌘V / ⌘A | copy / paste / select all |
| ⌘-click | open a `path:line` or a URL |

Right-click a pane to split or close it. Right-click the file tree for
**cd Here**, **New Tab Here**, **Insert Path** and **Copy Path**.

### Config

0xTerm reads `~/.config/0xterm/config.toml`, or
`$XDG_CONFIG_HOME/0xterm/config.toml` when that is set. Every key is
optional, and anything you leave out keeps the value shown here. Changes
apply to open windows as soon as you save.

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
cursor = "#e6e6e6"
selection = "#264f78"
# ansi = ["#1b1b1b", …16 colors]
```

`[theme.light]` takes the same keys. The full defaults are in
[`default.toml`](https://github.com/allocmemory/0xTerm/blob/main/crates/oxt-config/src/default.toml).

### How it is built

Bytes travel one way from the shell to the screen, and keys travel back:

```
zsh ⇄ pty ⇄ oxt-task (reader and writer threads)
              → oxt-session (alacritty_terminal: parser, grid, scrollback)
              → oxt-terminal-view (GPUI on Metal, one snapshot per frame)
```

A window holds tabs, each tab holds a tree of splits, and each split ends
in a pane running a shell. Beside them sits the toolbelt: the file tree,
folder search and the viewer. The toolbelt talks to the panes only through
events, such as "open this file at this line" or "the working folder
changed".

| Crate | What it does |
|---|---|
| `oxt-task` | pty, child process, reader and writer threads, cwd and foreground job |
| `oxt-session` | terminal state; key, paste and mouse encoding; OSC 7 |
| `oxt-terminal-view` | draws the grid; selection, links, input |
| `oxt-window` | tabs, splits, panes |
| `oxt-toolbelt` | file tree, folder search, viewer, Markdown and Mermaid |
| `oxt-config` | config file and themes |
| `app` | the `oxterm` binary: menus, windows, config reload |

0xTerm stands on [GPUI](https://www.gpui.rs) and
[gpui-component](https://github.com/longbridge/gpui-component) for the UI,
[alacritty_terminal](https://github.com/alacritty/alacritty) for terminal
emulation, [merman](https://github.com/Latias94/merman) and
[resvg](https://github.com/linebender/resvg) for diagrams, and ripgrep's
`ignore` and `grep` crates for search.

### Build from source

```sh
cargo run -p oxterm          # run a debug build
cargo test --workspace       # run the tests
packaging/bundle.sh          # build dist/0xTerm.app
packaging/dmg.sh             # build dist/0xTerm-<version>.dmg
packaging/install.sh         # build and install to /Applications
```

You need current stable Rust and Xcode. After installing Xcode, run
`sudo xcode-select -s /Applications/Xcode.app` and
`xcodebuild -downloadComponent MetalToolchain`.
