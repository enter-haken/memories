```
id: 9201518f-83fd-48ba-be70-139d6ce43964
title: asdf
links:
  - 5d895de8-3c19-11ea-8cff-93323f53bfc7
  - a5cc0346-169c-464f-9d1f-442e75959e6a
```

# asdf

## install

see [documentation][1]

## add plugins

if a `.tool-versions`  file like 

```
elixir 1.10.4
erlang 23.0.3
neovim nightly
nodejs 14.8.0
yarn 1.22.10
```

is present, you can install all necessary plugins by

```
for plugin in $(cat .tool-versions  | awk '{print $1}'); do asdf plugin add $plugin; done
```

after that, you can install all specified plugins by

```
$ asdf install
```

See also `plugin requirements` for each plugin.

[1]: https://asdf-vm.com/#/core-manage-asdf

