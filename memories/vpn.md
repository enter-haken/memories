```
id: f288d8ab-10bd-4afc-ad14-67c5d66f188d
title: OpenVPN
links:
  - 5d895de8-3c19-11ea-8cff-93323f53bfc7
```

# OpenVPN

* install `nmcli`

```
nmcli connection import type openvpn file *config filename*
nmcli connection modify id *config filename* vpn.user-name *user*
nmcli connection up *config filename*
```
