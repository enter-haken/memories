```
id: a5cc0346-169c-464f-9d1f-442e75959e6a
title: wsl
links:
  - 9f28bc28-cf1a-4011-ac29-19ff9a53d26a
  - 5d895de8-3c19-11ea-8cff-93323f53bfc7
```

# WSL

* Activate WSL according to [Microsoft][3]
* Install `Ubuntu 18.04 LTS`
* Checkout [dotfiles][1]
* Setup `ssh`
  * `ssh-keygen -o -t rsa -b 4096 _C "email@xxx.com"`
  * use same keys from `git installation` (`mingw`)
* Put new key into `gitlab`
* Setup `nord-theme`
  * see history.
  * see `wsltty`, `nord-mintty`, `mintty`
* Install `python`
  * `apt-get install python3-pip`
* install `tmux`
* install `ranger`
* Install `asdf`
* Install `tree`
* Install `neovim`
  * checkout [neovim config][2]

## Terminal

Add nord palete to terminal config

```
{
      "name": "nord",
      "black": "#3b4252",
      "red": "#bf616a",
      "green": "#a3be8c",
      "yellow": "#ebcb8b",
      "blue": "#81a1c1",
      "purple": "#b48ead",
      "cyan": "#88c0d0",
      "white": "#e5e9f0",
      "brightBlack": "#4c566a",
      "brightRed": "#bf616a",
      "brightGreen": "#a3be8c",
      "brightYellow": "#ebcb8b",
      "brightBlue": "#81a1c1",
      "brightPurple": "#b48ead",
      "brightCyan": "#8fbcbb",
      "brightWhite": "#eceff4",
      "background": "#2e3440",
      "foreground": "#d8dee9"
},
```

Update Ubuntu config

```
{
    "guid": "{07b52e3e-de2c-5db4-bd2d-ba144ed6c273}",
    "colorScheme": "nord",
    "hidden": false,
    "name": "Ubuntu-20.04",
    "source": "Windows.Terminal.Wsl",
    "commandLine": "wsl ~"
}
```

Setup default profile

```
"defaultProfile": "{07b52e3e-de2c-5db4-bd2d-ba144ed6c273}"
```

# further reading

[Docker-Container im Subsystem für Linux 2 (WSL 2) ausführen][4]

[1]: https://github.com/enter-haken/dotfiles
[2]: https://github.com/enter-haken/neovim-config
[3]: https://docs.microsoft.com/en-us/windows/wsl/install-win10
[4]: https://www.windowspro.de/wolfgang-sommergut/docker-container-subsystem-fuer-linux-2-wsl-2-ausfuehren
