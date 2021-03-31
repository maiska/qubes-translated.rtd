---
lang: fr
layout: doc
permalink: /fr/doc/templates/fedora/
ref: 136
title: The Fedora TemplateVM
---

# The Fedora TemplateVM
<a id="the-fedora-templatevm"></a>

The Fedora [TemplateVM] is the default TemplateVM in Qubes OS. This page is about the standard (or "full") Fedora TemplateVM. For the minimal and Xfce versions, please see the [Minimal TemplateVMs] and [Xfce TemplateVMs] pages.

## Installing
<a id="installing"></a>

To [install] a specific Fedora TemplateVM that is not currently installed in your system, use the following command in dom0:

```
$ sudo qubes-dom0-update qubes-template-fedora-XX
```

   (Replace `XX` with the Fedora version number of the template you wish to install.)

To reinstall a Fedora TemplateVM that is already installed in your system, see [How to Reinstall a TemplateVM].

## After Installing
<a id="after-installing"></a>

After installing a fresh Fedora TemplateVM, we recommend performing the following steps:

1. [Update the TemplateVM].

2. [Switch any TemplateBasedVMs that are based on the old TemplateVM to the new one][switch].

3. If desired, [uninstall the old TemplateVM].

## Updating
<a id="updating"></a>

For routine daily updates within a given release, see [Updating software in TemplateVMs].

## Upgrading
<a id="upgrading"></a>

There are two ways to upgrade your TemplateVM to a new Fedora release:

- [Install a fresh template to replace the existing one.](#installing) This option may be simpler for less experienced users. After you install the new template, redo all desired template modifications and [switch everything that was set to the old template to the new template][switch]. You may want to write down the modifications you make to your templates so that you remember what to redo on each fresh install. To see a log of package manager actions, open a terminal in the old Fedora template and use the `dnf history` command.

- [Perform an in-place upgrade of an existing Fedora template.][Upgrading Fedora TemplateVMs] This option will preserve any modifications you've made to the template, but it may be more complicated for less experienced users.

[TemplateVM]: /fr/doc/templates/
[Minimal TemplateVMs]: /fr/doc/templates/minimal/
[Xfce TemplateVMs]: /fr/doc/templates/xfce/
[end-of-life]: https://fedoraproject.org/wiki/Fedora_Release_Life_Cycle#Maintenance_Schedule
[supported]: /fr/doc/supported-versions/#templatevms
[How to Reinstall a TemplateVM]: /fr/doc/reinstall-template/
[Update the TemplateVM]: /fr/doc/software-update-vm/
[switch]: /fr/doc/templates/#switching
[uninstall the old TemplateVM]: /fr/doc/templates/#uninstalling
[Updating software in TemplateVMs]: /fr/doc/software-update-domu/#updating-software-in-templatevms
[Upgrading Fedora TemplateVMs]: /fr/doc/template/fedora/upgrade/
[install]: /fr/doc/templates/#installing