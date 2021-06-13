```
id: b6e1da42-3b6e-11ea-9662-078c609562a1
title: bash
links:
  - 16c0baea-4331-11ea-9889-83268609fc24
```

# Bourne again shell.

## calculate values with bc

```
function calc { echo "$1" | bc; }
export -f calc
```

# testing

* simple [unit testing framework][1] for bash.

# further reading

* [Linux Terminal Tools][2]
* [Command line secrets][3]

[1]: https://github.com/pgrange/bash_unit
[2]: https://ketancmaheshwari.github.io/pdfs/LPT_LISA.pdf
[3]: https://smallstep.com/blog/command-line-secrets/
