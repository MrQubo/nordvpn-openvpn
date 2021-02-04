Note to self: This script sucks.
It's broken, it's not removing tmp files, it's written in bash without even `set -o errexit`.
Good idea but poor execution. :/
Fow now not interested in fixing this.

Oh, great! The removal of package is also broken because it tries to download configuration files, which is broken because of outdated configuration file.

nordvpn-openvpn
=======

This is a fork of https://github.com/nstinus/nordvpn. It renames `nordvpn` to
`nordvpn-openvpn` so it can be installed alongside the `nordvpn-bin` AUR package.

Introduction
------------

`nordvpn-openvpn` is a command line helper script to use nordvpn.com for
systems with `openvpn` and `systemd`.
It was created for Arch Linux but should run without too much
difficulty on systems that satisfy the following dependency list:
- openvpn,
- systemd,
- curl,
- unzip,
- ping,
- openvpn-update-resolv-conf or vpnfailsafe.

Quickstart
----------

- Once installed, run `sudo nordvpn-openvpn update` to download and install the
configuration files.
- Edit `/etc/openvpn/client/nordvpn-openvpn/credentials.conf`.
- Run `sudo nordvpn-openvpn list` to choose a server (alternatively the `rank`
command pings the servers).
- Finally `sudo nordvpn-openvpn start <servername>`.
- The status command shows you the status of the systemd service.
- See `sudo nordvpn-openvpn -h` for more information.
