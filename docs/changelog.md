---
layout: default
title: Changelog
---

## Agent Panel v0.5.8

Released on 2026-02-24

### New Features

- feat: add root/non-root privilege filter and indicator across agent UI

### Bug Fixes

- fix: handle deleted binary and immutable flag in upgrade/hide
- fix: prevent duplicate upgrade commands and expire stale delivered commands
- fix: remove color distinction for root/non-root badge
- fix: use CircleUser icon for both root and non-root indicators

### All Changes

<details><summary>View all</summary>

- fix: handle deleted binary and immutable flag in upgrade/hide (afbd287)
- fix: prevent duplicate upgrade commands and expire stale delivered commands (dae9a6f)
- fix: remove color distinction for root/non-root badge (3b49869)
- fix: use CircleUser icon for both root and non-root indicators (9bc6986)
- feat: add root/non-root privilege filter and indicator across agent UI (36c1d52)
</details>

## Quick Install

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash
```
