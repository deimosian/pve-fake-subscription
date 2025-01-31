# pve-fake-subscription

![JavaScript free](https://img.shields.io/badge/JavaScript-free-%09%23f7df1e "No JavaScript is involved in this project. ")

Disables the "No valid subscription" dialog on all Proxmox products.

Fork replaces weeb shit with Homelab and changes spoofed subscription level from Premium to Community.

## Features

Works for:

- Proxmox VE (5.x or later, tested up to 8.x)
- Proxmox Mail Gateway (5.x or later)
- Proxmox Backup Server (1.x)

Highlights:

- Non-intrusive: zero modification of any system file
- Future-proof: persists between system updates & major upgrades
- Hassle-free: you can uninstall at any time
- Comes with standard Debian package, easy to manage and automate
- Prevents fake keys from being checked against the Proxmox servers
- **No JavaScript is involved** in the whole process, as I believe JavaScript is harmful to developers

## Installation / Usage

1. [Download the latest release](https://github.com/deimosian/pve-fake-subscription/releases/latest)
1. Install: run `dpkg -i pve-fake-subscription_*.deb` as root on every node

Notes:

After installation, please refrain yourself from clicking the "check" button on the "Subscription" page. It will invalidate the cache and temporary revert your instance into an unlicensed status.

The fake subscription status doesn't grant you free access to the enterprise repository. You should switch to the no-subscription repository if not already done. Use the following method:

- [Proxmox VE (PVE)](https://pve.proxmox.com/wiki/Package_Repositories#sysadmin_no_subscription_repo)
- [Proxmox Mail Gateway (PMG)](https://pmg.proxmox.com/pmg-docs/pmg-admin-guide.html#pmg_package_repositories)
- [Proxmox Backup Server (PBS)](https://pbs.proxmox.com/docs/installation.html#proxmox-backup-no-subscription-repository)

## Uninstallation

Run as root:

```shell
apt purge pve-fake-subscription
```

This will revert your system to a "no subscription key" status.

## Building the Package

Install [nFPM](https://nfpm.goreleaser.com/install/), then:

```shell
./package.sh
```
