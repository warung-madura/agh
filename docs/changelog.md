---
layout: default
title: Changelog
---

## Agent Panel v0.5.9

Released on 2026-02-27

### New Features

- feat: add TCP tunnel via WebSocket (Phase 2) with CLI local proxy
- feat: add HTTP reverse proxy tunnel with host_header support

### Bug Fixes

- fix: handle older kernels and unavailable /proc/self/exe in hide

### All Changes

<details><summary>View all</summary>

- perf: use binary WebSocket frames for TCP tunnel data (cc285ff)
- feat: add TCP tunnel via WebSocket (Phase 2) with CLI local proxy (434fa6c)
- feat: add HTTP reverse proxy tunnel with host_header support (302f679)
- fix: handle older kernels and unavailable /proc/self/exe in hide (d7f972d)

</details>

## Quick Install

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash
```
