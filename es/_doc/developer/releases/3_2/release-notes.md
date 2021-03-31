---
lang: es
layout: doc
permalink: /es/doc/releases/3.2/release-notes/
ref: 21
title: Qubes R3.2 release notes
---

# Qubes R3.2 release notes
<a id="qubes-r32-release-notes"></a>

## New features since 3.1
<a id="new-features-since-31"></a>

* Management Stack extended to support in-VM configuration - [documentation][salt-doc]
* PV USB - [documentation][usb]
* Dom0 update to Fedora 23 for better hardware support
* Kernel 4.4.x
* Default desktop environment switched to Xfce4
* KDE 5 support (but it is no longer the default one)
* Tiling window managers support: awesome, [i3][i3]
* More flexible Qubes RPC services - [related ticket][qrexec-argument], [documentation][qrexec-doc]

You can get detailed description in [completed github issues][github-release-notes]

## Known issues
<a id="known-issues"></a>

* [Fedora 23 reached EOL in December 2016](https://fedoraproject.org/wiki/End_of_life). There is a [manual procedure to upgrade your VMs](/news/2018/01/06/fedora-26-upgrade/).

* Windows Tools: `qvm-block` does not work

* Some icons in the Qubes Manager application might not be drawn correctly when using the Xfce4 environment in Dom0. If this bothers you, please use the KDE environment instead.

* For other known issues take a look at [our tickets](https://github.com/QubesOS/qubes-issues/issues?q=is%3Aopen+is%3Aissue+milestone%3A%22Release+3.2%22+label%3Abug)

It is advised to install updates just after system installation to apply bug fixes for (some of) the above problems.

## Downloads
<a id="downloads"></a>

See [Qubes Downloads](/es/downloads/).

## Installation instructions
<a id="installation-instructions"></a>

See [Installation Guide](/es/doc/installation-guide/).
After installation, [manually upgrade to Fedora 26](/news/2018/01/06/fedora-26-upgrade/).

## Upgrading
<a id="upgrading"></a>

### From R3.1
<a id="from-r31"></a>

The easiest and safest way to upgrade to Qubes R3.2 is to install it from
scratch and use [qubes backup and restore tools][backup] for
migrating of all of the user VMs.

Users of Qubes R3.1 can also upgrade using [this
procedure][upgrade].

### From R3.0 or earlier
<a id="from-r30-or-earlier"></a>

When upgrading from earlier versions the easiest and safest way is to install
it from scratch and use [qubes backup and restore tools][backup]
for migrating of all of the user VMs.

Alternatively you can [upgrade to R3.1 using][upgrade-r3.1] first, then follow
the instructions above. This will be time consuming process.

[salt-doc]: /es/doc/salt/
[usb]: /es/doc/usb/
[i3]: /es/doc/i3/
[upgrade]: /es/doc/upgrade-to-r3.2/
[upgrade-r3.1]: /es/doc/releases/3.1/release-notes/#upgrading
[backup]: /es/doc/backup-restore/
[qrexec-argument]: https://github.com/QubesOS/qubes-issues/issues/1876
[qrexec-doc]: /es/doc/qrexec/#service-policies-with-arguments
[github-release-notes]: https://github.com/QubesOS/qubes-issues/issues?q=is%3Aissue+sort%3Aupdated-desc+milestone%3A%22Release+3.2%22+label%3Arelease-notes+is%3Aclosed