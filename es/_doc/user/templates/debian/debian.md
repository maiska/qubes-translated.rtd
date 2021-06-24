---
lang: es
layout: doc
permalink: /es/doc/templates/debian/
redirect_from:
- /es/doc/Templates/Debian/
- /es/doc/debian/
- /es/wiki/Templates/Debian/
ref: 134
title: Debian Templates
---

The Debian [template](/es/doc/templates/) is an officially [supported](/es/doc/supported-versions/#templates) template in Qubes OS.
This page is about the standard (or "full") Debian template.
For the minimal version, please see the [Minimal templates](/es/doc/templates/minimal/) page.
There is also a [Qubes page on the Debian Wiki](https://wiki.debian.org/Qubes).

## Installing
<a id="installing"></a>

To [install](/es/doc/templates/#installing) a specific Debian template that is not currently installed in your system, use the following command in dom0:

```
$ sudo qubes-dom0-update qubes-template-debian-XX
```

   (Replace `XX` with the Debian version number of the template you wish to install.)

To reinstall a Debian template that is already installed in your system, see [How to Reinstall a template](/es/doc/reinstall-template/).

## After Installing
<a id="after-installing"></a>

After installing a fresh Debian template, we recommend performing the following steps:

1. [Update the template](/es/doc/software-update-vm/).

2. [Switch any app qubes that are based on the old template to the new one](/es/doc/templates/#switching).

3. If desired, [uninstall the old template](/es/doc/templates/#uninstalling).

## Installing software
<a id="installing-software"></a>

See [How to Install Software](/es/doc/how-to-install-software/).

## Updating
<a id="updating"></a>

For routine daily updates within a given release, see [How to Update](/es/doc/how-to-update/).

## Upgrading
<a id="upgrading"></a>

There are two ways to upgrade your template to a new Debian release:

- **Recommended:** [Install a fresh template to replace the existing one.](#installing) **This option may be simpler for less experienced users.** After you install the new template, redo all desired template modifications and [switch everything that was set to the old template to the new template](/es/doc/templates/#switching). You may want to write down the modifications you make to your templates so that you remember what to redo on each fresh install. In the old Debian template, see `/var/log/dpkg.log` and `/var/log/apt/history.log` for logs of package manager actions.

- **Advanced:** [Perform an in-place upgrade of an existing Debian template.](/es/doc/template/debian/upgrade/) This option will preserve any modifications you've made to the template, **but it may be more complicated for less experienced users.**

## Release-specific notes
<a id="release-specific-notes"></a>

This section contains notes about specific Debian releases.

### Debian 10
<a id="debian-10"></a>

Debian 10 (buster) - minimal:

```
[user@dom0 ~]$ sudo qubes-dom0-update --enablerepo=qubes-templates-itl qubes-template-debian-10-minimal
```

Debian 10 (buster) - stable:

```
[user@dom0 ~]$ sudo qubes-dom0-update --enablerepo=qubes-templates-itl qubes-template-debian-10
```

### Starting services
<a id="starting-services"></a>

The Debian way (generally) is to start daemons if they are installed.
This means that if you install (say) ssh-server in a template, *all* the qubes that use that template will run a ssh server when they start. (They will, naturally, all have the same server key.) This may not be what you want.

So be very careful when installing software in Templates - if the daemon spawns outbound connections then there is a serious security risk.

In general, a reasonable approach would be, (using ssh as example):

- Install the ssh service.
- `systemctl stop ssh`
- `systemctl disable ssh`
- `systemctl mask ssh`
- Close down template

Now the ssh service will **NOT** start in qubes based on this template.

Where you **DO** want the service to run, put this in `/rw/config/rc.local`:

```
systemctl unmask ssh
systemctl start ssh
```

Don't forget to make the file executable.

### Unattended Upgrades
<a id="unattended-upgrades"></a>

Some users have noticed that on upgrading to Stretch, the `unattended-upgrade` package is installed.

This package is pulled in as part of a Recommend chain, and can be purged.

The lesson is that you should carefully look at what is being installed to your system, particularly if you run `dist-upgrade`.

### Package installation errors in Qubes 4.0
<a id="package-installation-errors-in-qubes-40"></a>

If some packages throw installation errors, see [this guide.](/es/doc/vm-troubleshooting/#fixing-package-installation-errors)