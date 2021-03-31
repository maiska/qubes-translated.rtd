---
lang: de
layout: doc
permalink: /de/doc/templates/debian/
redirect_from:
- /de/doc/Templates/Debian/
- /de/doc/debian/
- /de/wiki/Templates/Debian/
ref: 134
title: The Debian TemplateVM
---

# The Debian TemplateVM
<a id="the-debian-templatevm"></a>

The Debian [TemplateVM] is an officially [supported] TemplateVM in Qubes OS.
This page is about the standard (or "full") Debian TemplateVM.
For the minimal version, please see the [Minimal TemplateVMs] page.
There is also a [Qubes page on the Debian Wiki].

## Installing
<a id="installing"></a>

To [install] a specific Debian TemplateVM that is not currently installed in your system, use the following command in dom0:

```
$ sudo qubes-dom0-update qubes-template-debian-XX
```

   (Replace `XX` with the Debian version number of the template you wish to install.)

To reinstall a Debian TemplateVM that is already installed in your system, see [How to Reinstall a TemplateVM].

## After Installing
<a id="after-installing"></a>

After installing a fresh Debian TemplateVM, we recommend performing the following steps:

1. [Update the TemplateVM].

2. [Switch any TemplateBasedVMs that are based on the old TemplateVM to the new one][switch].

3. If desired, [uninstall the old TemplateVM].

## Updating
<a id="updating"></a>

For routine daily TemplateVM updates within a given Debian release, see [Updating software in TemplateVMs].

## Upgrading
<a id="upgrading"></a>

There are two ways to upgrade your TemplateVM to a new Debian release:

- [Install a fresh template to replace the existing one.](#installing) This option may be simpler for less experienced users. After you install the new template, redo all desired template modifications and [switch everything that was set to the old template to the new template][switch]. You may want to write down the modifications you make to your templates so that you remember what to redo on each fresh install. In the old Debian template, see `/var/log/dpkg.log` and `/var/log/apt/history.log` for logs of package manager actions.

- [Perform an in-place upgrade of an existing Debian template.][Upgrading Debian TemplateVMs] This option will preserve any modifications you've made to the template, but it may be more complicated for less experienced users.

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

If some packages throw installation errors, see [this guide.](/de/doc/vm-troubleshooting/#fixing-package-installation-errors)

[TemplateVM]: /de/doc/templates/
[Minimal TemplateVMs]: /de/doc/templates/minimal/
[Qubes page on the Debian Wiki]: https://wiki.debian.org/Qubes
[end-of-life]: https://wiki.debian.org/DebianReleases#Production_Releases
[supported]: /de/doc/supported-versions/#templatevms
[How to Reinstall a TemplateVM]: /de/doc/reinstall-template/
[Update the TemplateVM]: /de/doc/software-update-vm/
[switch]: /de/doc/templates/#switching
[uninstall the old TemplateVM]: /de/doc/templates/#uninstalling
[Updating software in TemplateVMs]: /de/doc/software-update-domu/#updating-software-in-templatevms
[Upgrading Debian TemplateVMs]: /de/doc/template/debian/upgrade/
[5149]: https://github.com/QubesOS/qubes-issues/issues/5149
[install]: /de/doc/templates/#installing