```
id: 79cea057-2577-4340-8f53-1bfe29cc2cb3
title: Alacritty
  - 3da4e373-670d-4a8b-b2f1-865e02324840
```

# Alacritty

Install via `cargo`

```
$ cargo install alacritty
```

## nord theme

add the following content to `$XDG_CONFIG_HOME/alacritty/alacritty.yml`

```
# Copyright (c) 2017-present Arctic Ice Studio <development@arcticicestudio.com>
# Copyright (c) 2017-present Sven Greb <code@svengreb.de>

# Project:    Nord Alacritty
# Version:    0.1.0
# Repository: https://github.com/arcticicestudio/nord-alacritty
# License:    MIT
# References:
#   https://github.com/alacritty/alacritty
#
env:
  TERM: 'xterm-256color'

colors:
  primary:
    background: '#2e3440'
    foreground: '#d8dee9'
    dim_foreground: '#a5abb6'
  cursor:
    text: '#2e3440'
    cursor: '#d8dee9'
  vi_mode_cursor:
    text: '#2e3440'
    cursor: '#d8dee9'
  selection:
    text: CellForeground
    background: '#4c566a'
  search:
    matches:
      foreground: CellBackground
      background: '#88c0d0'
    bar:
      background: '#434c5e'
      foreground: '#d8dee9'
  normal:
    black: '#3b4252'
    red: '#bf616a'
    green: '#a3be8c'
    yellow: '#ebcb8b'
    blue: '#81a1c1'
    magenta: '#b48ead'
    cyan: '#88c0d0'
    white: '#e5e9f0'
  bright:
    black: '#4c566a'
    red: '#bf616a'
    green: '#a3be8c'
    yellow: '#ebcb8b'
    blue: '#81a1c1'
    magenta: '#b48ead'
    cyan: '#8fbcbb'
    white: '#eceff4'
  dim:
    black: '#373e4d'
    red: '#94545d'
    green: '#809575'
    yellow: '#b29e75'
    blue: '#68809a'
    magenta: '#8c738c'
    cyan: '#6d96a5'
    white: '#aeb3bb'
```

At the time of writing, I use the `term` settings when you do a `ssh` to a remote server. 
This is only a work around.