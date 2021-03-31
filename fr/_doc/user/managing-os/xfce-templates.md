---
lang: fr
layout: doc
permalink: /fr/doc/templates/xfce/
redirect_from:
- /fr/doc/xfce/
- /fr/doc/Templates/Xfce/
- /fr/wiki/Templates/Xfce/
ref: 222
title: Xfce TemplateVMs
---

# Xfce TemplateVMs
<a id="xfce-templatevms"></a>

If you would like to use Xfce (more lightweight compared to GNOME desktop environment) Linux distribution in your qubes,
you can install one of the available Xfce templates for [Fedora], [CentOS] or [Gentoo].

## Installation
<a id="installation"></a>

The Fedora Xfce TemplateVMs can be installed with the following command (where `X` is your desired distro and version number):

```
[user@dom0 ~]$ sudo qubes-dom0-update qubes-template-X-xfce
```

If your desired version is not found, it may still be in [testing].
You may wish to try again with the testing repository enabled:

```
[user@dom0 ~]$ sudo qubes-dom0-update --enablerepo=qubes-templates-itl-testing qubes-template-X-xfce
```

If you would like to install a community distribution, like CentOS or Gentoo, try the install command by enabling the community repository:

```
[user@dom0 ~]$ sudo qubes-dom0-update --enablerepo=qubes-templates-community qubes-template-X-xfce
```

If your desired version is not found, it may still be in [testing].
You may wish to try again with the testing repository enabled:

```
[user@dom0 ~]$ sudo qubes-dom0-update --enablerepo=qubes-templates-community-testing qubes-template-X-xfce
```

The download may take a while depending on your connection speed.

To reinstall a Xfce TemplateVM that is already installed in your system, see [How to Reinstall a TemplateVM].

[How to Reinstall a TemplateVM]: /fr/doc/reinstall-template/
[TemplateVMs]: /fr/doc/templates/
[Fedora]: /fr/doc/templates/fedora/
[Debian]: /fr/doc/templates/debian/
[CentOS]: /fr/doc/templates/centos/
[Gentoo]: /fr/doc/templates/gentoo/
[testing]: /fr/doc/testing/