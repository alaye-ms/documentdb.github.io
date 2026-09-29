---
title: "DocumentDB Version Standards for 1.0 and Beyond"
description: A guide to how we update DocumentDB and the standards for future updates.
date: 2026-09-29
featured: true
author: DocumentDB team
category: documentdb-blog
tags:
  - DocumentDB
  - "1.0"
  - Release
  - Version
---
Now that DocumentDB is releasing its 1.0 version, it is important to clarify what exactly a major version bump means, and how we plan on moving forward with version changes. In brief, major versions will release every year, and we will support each major release until three months after the next major comes out. Minor releases will continue to update on a roll-forward basis.

## Annual major releases

DocumentDB will publish one new major version each year. The next major version is developed on `main`; supported major versions are maintained on branches such as `release/v3`. We will continue to build artifacts for the latest minor release alongside the supported major versions.

When a new major version begins support, a release branch is created and artifacts are built. The previous major version then enters a three-month grace period before support ends. Security fixes will be backported to supported release branches, with new artifacts built until support ends. Other bug fixes will be backported case by case.

## Release candidates

Release candidates use the `-RC` suffix. For example, a release candidate for version 3 could be tagged `v3.0-RC1`, followed by a final release tag such as `v3.0-0`. After the final release, `release/v3` becomes the supported branch for version 3, while `main` moves on to development for version 4. The previous `release/v2` branch remains supported during its grace period.

## What belongs in major, minor, and patch releases

Major releases are only time-based. They happen yearly and will include instructions for updating from previous long-term supported major versions. That means that minor updates can include all breaking changes, such as removal of support for PostgreSQL dependencies, 

## Upgrade path

DocumentDB will support direct in-place upgrades between consecutive major versions. There is also a simple path from the current major release to the latest minor release of that same major. This will allow for a simple switch from long-term support to the latest builds.

Release candidates are different. Upgrades from release candidate versions will not be supported. Release candidates use the same extension version as the first full release for that major, so there is no reliable extension upgrade path from an RC to the final release.
