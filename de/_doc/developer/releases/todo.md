---
lang: de
layout: doc
permalink: /de/doc/releases/todo/
redirect_from: []
ref: 14
title: Release Checklist
---

Release Checklist
=================
<a id="release-checklist"></a>

*the checklist is probably unfinished*

On -rc1
-------
<a id="on--rc1"></a>

* write schedule
* create package repositories (linux-yum, linux-deb)
* update repository definition (core-agent-linux, installer-qubes-os/qubes-release)
* push all packages to `current-testing`
* draft release notes, one note per feature
* create upgrade package in previous release branch (r2->r3.0, r3.0->r3.1, etc) - core-agent-linux
* make sure that keys for the current release are included in previous release's qubes-release package (for upgrade)
* build ISO and push to mirrors

On subsequent -rc
-----------------
<a id="on-subsequent--rc"></a>

* push packages to `current`
* update release notes
* build ISO and push to mirrors
* notify @Rudd-O about the new ISO for new torrent hosting

On final release
----------------
<a id="on-final-release"></a>

* push packages to `current`
* finish release notes
* update InstallationInstructions
* build ISO and push to mirrors
* notify @Rudd-O about the new ISO for new torrent hosting
* write blog post
* announce on Twitter