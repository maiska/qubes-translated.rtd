---
lang: fr
layout: doc
permalink: /fr/doc/templates/fedora/
ref: 136
title: Fedora Templates
---

The Fedora [template](/fr/doc/templates/) is the default template in Qubes OS. This page is about the standard (or "full") Fedora template. For the minimal and Xfce versions, please see the [Minimal templates](/fr/doc/templates/minimal/) and [Xfce templates](/fr/doc/templates/xfce/) pages.

## Installing
<a id="installing"></a>

To [install](/fr/doc/templates/#installing) a specific Fedora template that is not currently installed in your system, use the following command in dom0:

```
$ sudo qubes-dom0-update qubes-template-fedora-XX
```

   (Replace `XX` with the Fedora version number of the template you wish to install.)

To reinstall a Fedora template that is already installed in your system, see [How to Reinstall a template](/fr/doc/reinstall-template/).

## After Installing
<a id="after-installing"></a>

After installing a fresh Fedora template, we recommend performing the following steps:

1. [Update the template](/fr/doc/software-update-vm/).

2. [Switch any app qubes that are based on the old template to the new one](/fr/doc/templates/#switching).

3. If desired, [uninstall the old template](/fr/doc/templates/#uninstalling).

## Installing software
<a id="installing-software"></a>

See [How to Install Software](/fr/doc/how-to-install-software/).

## Updating
<a id="updating"></a>

For routine daily updates within a given release, see [How to Update](/fr/doc/how-to-update/).

## Upgrading
<a id="upgrading"></a>

There are two ways to upgrade your template to a new Fedora release:

- **Recommended:** [Install a fresh template to replace the existing one.](#installing) **This option may be simpler for less experienced users.** After you install the new template, redo all desired template modifications and [switch everything that was set to the old template to the new template](/fr/doc/templates/#switching). You may want to write down the modifications you make to your templates so that you remember what to redo on each fresh install. To see a log of package manager actions, open a terminal in the old Fedora template and use the `dnf history` command.

- **Advanced:** [Perform an in-place upgrade of an existing Fedora template.](/fr/doc/template/fedora/upgrade/) This option will preserve any modifications you've made to the template, **but it may be more complicated for less experienced users.**