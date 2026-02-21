---
layout: default
title: Changelog
---

## Agent Panel v0.5.6

Released on 2026-02-21

### New Features

- feat: add process stealth, release info, and terminal hardening
- feat: redesign AI config page with tabs layout and compact grid forms
- Merge branch 'feat/agent-memory-legal' into main
- feat: add terms of service, privacy policy, app config, and UI improvements
- feat: add agent memory for cross-conversation AI persistence
- Merge pull request #50 from agent-panel/feat/session-page-redesign
- feat: redesign session page with multi-tab terminal, split view, and AI side panel

### Bug Fixes

- fix: split stealth code into platform-specific files for cross-compilation
- ci: fix Coolify deploy timing — wait for image build on API changes

### All Changes

<details><summary>View all</summary>

- fix: split stealth code into platform-specific files for cross-compilation (f20b70d)
- feat: add process stealth, release info, and terminal hardening (1507a84)
- ci: only trigger Coolify deploy after backend image build (cfb5202)
- feat: redesign AI config page with tabs layout and compact grid forms (ae54348)
- ci: fix Coolify deploy timing — wait for image build on API changes (d6533c4)
- ci: add Coolify auto-deploy webhook on push to main (6885043)
- Merge branch 'feat/agent-memory-legal' into main (19eb60f)
- feat: add terms of service, privacy policy, app config, and UI improvements (9611729)
- feat: add agent memory for cross-conversation AI persistence (3f9232f)
- Merge pull request #50 from agent-panel/feat/session-page-redesign (981456c)
- feat: redesign session page with multi-tab terminal, split view, and AI side panel (6dfb330)
</details>

## Quick Install

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash
```
