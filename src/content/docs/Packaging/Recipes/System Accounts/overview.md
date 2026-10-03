---
title: 'Overview'
lastUpdated: 2026-10-02T15:00:00Z
description: "Stateless management of aerynOS user accounts"
license: "CC-BY-SA-4.0"
copyright: "Copyright © 2025 aerynOS Developers"
---

As a stateless distribution, aerynOS does not permit the modification of `/etc/passwd` and co by packages or triggers. Instead, we integrate `nss-systemd` and `userdb`.

:::caution
The use of `nss` means that user accounts and groups defined by this mechanism are only available to packages using the correct `glibc` APIs. Statically linking with `musl` or directly reading `/etc/passwd`, `/etc/group`, etc, will not reveal these accounts.
:::

The main benefit with this approach is ensuring that we do not directly mutate system files, and that unlike the `sysusers` mechanism, removal of a package ensures these system user and group definitions are no longer available.
