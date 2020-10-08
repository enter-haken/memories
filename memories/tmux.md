```
id: 4761c340-3c1c-11ea-8c71-2bd62160c2bd
title: tmux
links:
  - abaa8394-3c19-11ea-b9ab-1fa8afe8f1a2
```

To use `tmux` with 256 colors your `~/.tmux.conf` should contain should contain

```
set -g default-terminal "screen-256color"
```

The `XTERM` environment variable must be set to `xterm-256color`.

You can create an alias like

```
alias tmux="TERM=xterm-256color tmux"
```

for convenience.


