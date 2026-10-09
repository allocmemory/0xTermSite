+++
title = "Features"
description = "What 0xTerm v0.1 does: GPU drawing, splits, a file tree that follows the shell, a file viewer, Markdown and Mermaid preview."
+++

<p class="status">These are the targets for v0.1. 0xTerm is in development,
and nothing on this page ships before then.</p>

### Drawn by the GPU

The terminal grid is painted through Metal every frame: one pass for
backgrounds, one for shaped text, one for the cursor and selection.
Parsing runs on its own thread, so a flood of output never blocks typing.

### A real login shell

Each pane runs your shell as a login shell on its own pty, with
`TERM=xterm-256color` and truecolor. Launching from the Dock still gets
your `PATH`.

### Split panes

Split right with ⌘D and down with ⇧⌘D, then drag the divider. Inactive
panes dim, so you always know where your keys are going. A pane shows a
title only when its tab holds more than one.

### Tabs that say what is running

A tab is named after its foreground job, like `vim` or `htop`, and falls
back to the folder name when the shell is idle. Tabs share one row with the
window buttons, so the title bar takes no extra space.

### A file tree that follows your shell

The sidebar shows the folder your active pane is in. `cd` and it follows,
through OSC 7 when the shell sends it and the process table when it doesn't.
Folders come first, `.git` and `.gitignore`d files stay out of the way, and
the tree updates live as files change.

### Search the folder

Type in the sidebar and the whole folder is searched, ripgrep-style, off
the main thread. Hits are grouped by file. Click one and it opens at that
line, with the match highlighted.

### A file viewer beside the shell

Click a file and it opens on the right with syntax highlighting, line
numbers and ⌘F find with a match count. It reloads when the file changes on
disk, so you can edit in the terminal and read the result next to it.

### Markdown and Mermaid preview

Markdown renders as a document, with a Source toggle. Mermaid diagrams are
drawn natively, with no browser inside the app, and follow light and dark
mode. Relative links open in the viewer.

### ⌘-click a path

Any `path:line` in the terminal is a link. ⌘-click it and the viewer opens
the file at that line, resolved against the pane's working folder. URLs
open in your browser, and OSC 8 hyperlinks work too.

### Drag a file in

Drag a file from the tree onto a pane and its quoted path is typed at the
prompt. Right-click the tree for cd Here, New Tab Here, Insert Path and
Copy Path.

### One config file

Font, size, shell, scrollback and both color palettes live in
`~/.config/0xterm/config.toml`. Anything you leave out keeps its default.
The theme follows the system's light and dark mode unless you pin one.
