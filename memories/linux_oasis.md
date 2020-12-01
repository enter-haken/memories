```
id: eef0426e-58c9-434a-9acc-02997e2295d8
title: oasis
links:
  - 5d895de8-3c19-11ea-8cff-93323f53bfc7
```

# staticaly linked linux

[oasis][1] is a small linux system.

* Completely statically linked.
* Fast builds that are 100% reproducible.
* Minimal bootstrap dependencies.
* BearSSL is the system TLS and crypto library.
* No package manager.
* Integrates well with OS-agnostic package systems.
* Extremely simple system configuration.
* Mostly ISO C conformant.

oasis uses smaller and simpler implementations of libraries and tools whenever possible:

* musl instead of glibc
* sbase instead of coreutils
* ubase instead of util-linux
* pigz instead of gzip
* mandoc instead of man-db
* bearssl instead of openssl
* oksh instead of bash
* sdhcp instead of dhclient or dhcpcd
* vis instead of vim or emacs
* bc-gh instead of GNU bc
* byacc instead of bison
* perp and sinit instead of sysvinit or systemd
* netsurf instead of chromium or firefox
* samurai instead of ninja
* velox instead of Xorg

[1]: https://github.com/oasislinux/oasis
