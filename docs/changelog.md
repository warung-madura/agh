---
layout: default
title: Changelog
---

## Agent Panel v0.4.0

Released on 2026-02-12

### New Features

- feat: add offline handling for terminal and file manager sessions
- feat: add agent upgrade system with GitHub release integration
- feat: add agents page filter, search, sort, pagination, rename, delete, and grid/table view
- feat: add new file, upload, and large file handling to file explorer

### Bug Fixes

- fix: correct useAgents call signature for refetchInterval
- fix: show dotfiles by default and disable quick actions for offline agents
- fix: improve onboarding page with proper install commands and error handling
- feat: add agent upgrade system with GitHub release integration

### All Changes

<details><summary>View all</summary>

- fix: correct useAgents call signature for refetchInterval (0ed30b5)
- feat: add offline handling for terminal and file manager sessions (333c18d)
- fix: show dotfiles by default and disable quick actions for offline agents (8988b6f)
- fix: improve onboarding page with proper install commands and error handling (c1e35d1)
- feat: add agent upgrade system with GitHub release integration (fb07fce)
- feat: add agents page filter, search, sort, pagination, rename, delete, and grid/table view (b4550c5)
- feat: add new file, upload, and large file handling to file explorer (c24e462)
</details>

## Quick Install

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash
```
