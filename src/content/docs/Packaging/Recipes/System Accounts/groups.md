---
title: 'Groups'
lastUpdated: 2026-10-02T15:00:00Z
description: "Stateless management of system group accounts"
license: "CC-BY-SA-4.0"
copyright: "Copyright © 2025 aerynOS Developers"
---

Refer to the [JSON Group Record](https://systemd.io/GROUP_RECORD/) documentation for information on all supported fields.

## Example

Within the package tree `./pkg` add `gdm.group`:

```json
{
    "groupName" : "gdm",
    "gid" : 21,
    "disposition" : "system"
}
```

Note that these are the minimum required set of fields, and `disposition` should always be set to `system`.

In your recipe's `install` section, you must install the file by group name *and* by gid to the `%(libdir)/userdb` directory:

```shell
    %install_file %(pkgdir)/gdm.group %(installroot)%(libdir)/userdb/gdm.group
    ln -s gdm.group %(installroot)%(libdir)/userdb/21.group
```
