---
lang: de
layout: doc
permalink: /de/security/
redirect_from:
- /de/doc/QubesSecurity/
- /de/doc/SecurityPage/
- /de/doc/qubes-security/
- /de/doc/security-page/
- /de/doc/security/
- /de/trac/wiki/SecurityPage/
- /de/wiki/QubesSecurity/
- /de/wiki/SecurityPage/
ref: 217
title: Qubes OS Project Security Center
---

This page provides a central hub for topics pertaining to the security of the
Qubes OS Project. For topics pertaining to software security *within* Qubes OS,
see [Security in Qubes](/de/doc/#security-in-qubes). The following is a list of
important project security pages:

- [Qubes Security Pack (`qubes-secpack`)](/de/security/pack/)
- [Qubes Security Bulletins (QSBs)](/de/security/qsb/)
- [Qubes Canaries](/de/security/canary/)
- [Xen Security Advisory (XSA) Tracker](/de/security/xsa/)
- [Verifying signatures](/de/security/verifying-signatures/)
- [PGP keys](https://keys.qubes-os.org/keys/)
- [Security FAQ](/de/faq/#general--security)

## Reporting Security Issues in Qubes OS
<a id="reporting-security-issues-in-qubes-os"></a>

If you believe you have found a security issue affecting Qubes OS, either
directly or indirectly (e.g., the issue affects Xen in a configuration that is
used in Qubes OS), then we would be more than happy to hear from you! Please
send a [PGP-encrypted](#security-team-pgp-key) email to the [Qubes Security
Team](#qubes-security-team). We promise to take all reported issues seriously.
If our investigation confirms that an issue affects Qubes, we will patch it
within a reasonable time and release a public [Qubes Security Bulletin
(QSB)](/de/security/qsb/) that describes the issue, discusses the potential impact
of the vulnerability, references applicable patches or workarounds, and credits
the discoverer.

## Security Updates
<a id="security-updates"></a>

Qubes security updates are obtained by [updating Qubes
OS](/de/doc/how-to-update/).

## Qubes Security Team
<a id="qubes-security-team"></a>

The **Qubes Security Team (QST)** is the subset of the [Core Qubes
Team](/de/team/#core-team) that is responsible for ensuring the security of Qubes OS
and the Qubes OS Project. In particular, the QST is responsible for:

- Responding to [reported security
  issues](#reporting-security-issues-in-qubes-os)
- Evaluating whether [XSAs](/de/security/xsa/) affect the security of Qubes OS
- Writing, applying, and/or distributing security patches to fix
  vulnerabilities in Qubes OS
- Writing, signing, and publishing [Qubes Security Bulletins
  (QSBs)](/de/security/qsb/)
- Writing, signing, and publishing [Qubes Canaries](/de/security/canary/)
- Generating, safeguarding, and using the project's [PGP
  keys](https://keys.qubes-os.org/keys/)

As a security-oriented operating system, the QST is fundamentally important to
Qubes, and every Qubes user implicitly trusts the members of the QST by virtue
of the actions listed above. The Qubes Security Team can be contacted via email
at the following address:

```
security at qubes-os dot org
```

### Security Team PGP Key
<a id="security-team-pgp-key"></a>

Please use the [Security Team PGP
Key](https://keys.qubes-os.org/keys/qubes-os-security-team-key.asc) to encrypt
all emails sent to this address. This key is signed by the [Qubes Master
Signing Key](https://keys.qubes-os.org/keys/qubes-master-signing-key.asc).
Please see [Verify Signatures](/de/security/verifying-signatures/) for information
about how to authenticate these keys.

### Members of the Security Team
<a id="members-of-the-security-team"></a>

- [Marek Marczykowski-Górecki](/de/team/#marek-marczykowski-górecki)
- [Simon Gaiser (aka HW42)](/de/team/#simon-gaiser-aka-hw42)
- [Joanna Rutkowska](/de/team/#joanna-rutkowska) ([emeritus, canaries only](/news/2018/11/05/qubes-security-team-update/))