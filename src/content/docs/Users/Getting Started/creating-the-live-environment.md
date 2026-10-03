---
title: Creating the Live Environment
lastUpdated: 2026-10-02T15:00:00Z
description: Creating a live environment to boot into and run the aerynOS installer
license: "CC-BY-SA-4.0"
copyright: "Copyright © 2025 aerynOS Developers"
---

# Creating a Bootable USB Drive

## Prerequisites

- Instructions for [Downloading aerynOS](/users/getting-started/downloading/).
- You will need a spare USB drive that you don't mind wiping.

## Preparing an install medium using Etcher

1. Download the latest version of [Balena Etcher](https://etcher.balena.io/) for your OS.
2. Launch the application
3. Select the latest aerynOS ISO you have already downloaded
4. Select the inserted USB stick
5. Flash!
6. Ensure the USB drive is properly ejected after flashing the ISO to avoid data corruption.

:::danger
Creating a bootable USB drive using Etcher will erase all data on the USB drive. Make sure to back up any important data before proceeding.
:::

### Alternative options

There are several alternative options that can be used for creating a bootable USB drive. These include, but are not limited to:

- **Rufus**: A free and open-source tool for Windows that can create bootable USB drives.
- **dd**: A Linux command-line utility that can be used to create bootable USB drives from the command line.
- **GNOME Disks**: A graphical tool that can be used to create bootable USB drives on Linux.

You can find instructions for these various options online via your favorite search engine.
