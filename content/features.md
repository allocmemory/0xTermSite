+++
title = "Features"
description = "What 0xTerm does: GPU drawing, tabs and splits, a file tree that follows the shell, folder search, a file viewer, Markdown and Mermaid preview."
+++

### Drawn by the GPU

The terminal grid is painted through Metal every frame, in 16, 256 or
truecolor, with bold, italic, underline and wide characters. Parsing runs
on its own thread, so a flood of output never blocks typing.

### A real login shell

Each pane runs your shell as a login shell on its own pty, with
`TERM=xterm-256color` and truecolor. Launching from the Dock still gets
your `PATH`.

### A terminal that behaves

Scrollback, mouse selection by word, line or block, copy and paste,
bracketed paste, mouse reporting, focus events, synchronized updates and
IME input. Block, bar and underline cursors.

### Tabs and splits

Split right with ⌘D and down with ⇧⌘D, then drag the divider. Inactive
panes dim, so you always know where your keys are going. A tab is named
after its running job, like `vim` or `htop`, and falls back to the folder
name. Tabs share one row with the window buttons, so the title bar takes no
extra space.

### A file tree that follows your shell

The sidebar shows the folder your active pane is in. `cd` and it follows,
through OSC 7 when the shell sends it and the process table when it
doesn't. Folders come first, `.git` and `.gitignore`d files stay out of the
way, and the tree updates live as files change.

### Search the folder

⇧⌘F searches the whole folder, ripgrep-style, off the main thread. Hits are
grouped by file. Click one and it opens at that line.

### A file viewer beside the shell

Click a file and it opens on the right with syntax highlighting, line
numbers and ⌘F find with a match count. It reloads when the file changes on
disk, so you can edit in the terminal and read the result next to it.

### Markdown and Mermaid preview

Markdown renders as a document. Mermaid diagrams are drawn natively, with
no browser inside the app, and follow light and dark mode.

### ⌘-click a path

Any `path:line` in the terminal is a link. ⌘-click it and the viewer opens
the file at that line, resolved against the pane's working folder. URLs
open in your browser, and OSC 8 hyperlinks work too.

### Drag a file in

Drag a file from the tree onto a pane and its quoted path is typed at the
prompt. Right-click the tree for **cd Here**, **New Tab Here**, **Insert
Path** and **Copy Path**.

### One config file

Font, size, shell, scrollback and both color palettes live in
`~/.config/0xterm/config.toml`. Changes apply to open windows as soon as
you save. The theme follows the system's light and dark mode unless you pin
one.

### Native on the Mac

Native menus, a Dock icon, ⌘N for new windows and a DMG installer.
