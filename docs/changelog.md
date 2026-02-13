---
layout: default
title: Changelog
---

## Agent Panel v0.5.2

Released on 2026-02-13

### New Features

- Merge pull request #44 from agent-panel/dev/initial-scaffold
- feat: add version guard for terminate action (min v0.5.2)
- feat: add public_ip and connect_ip fields for full agent IP tracking
- feat: add agent terminate action for graceful remote shutdown
- Dev/initial scaffold (#39)
- Dev/initial scaffold (#38)
- Dev/initial scaffold (#37)
- Dev/initial scaffold (#36)
- feat: reorganize agent detail page with tabbed interface
- Dev/initial scaffold (#35)
- feat: add swipe-to-delete for conversation list items
- fix: include tool execution results in conversation history (#34)
- feat: add delete conversation functionality across all layers (#33)
- feat: add delete conversation functionality across all layers
- Merge pull request #27 from agent-panel/dev/initial-scaffold
- feat: show symlink bug warning in upgrade dialog for agents < v0.5.1

### Bug Fixes

- fix: ensure agent process exits on terminate and add self-cleanup
- Merge pull request #43 from agent-panel/dev/initial-scaffold
- fix: handle timeout field as string or number in run_command
- Merge pull request #42 from agent-panel/dev/initial-scaffold
- fix: ListPendingToolExecutions now includes approved/rejected tools
- Merge pull request #41 from agent-panel/dev/initial-scaffold
- fix: use total_items instead of items.length for dashboard agent count
- fix: prevent long conversation titles from hiding trash button
- Dev/initial scaffold (#39)
- fix: skip incomplete assistant messages to prevent Claude API tool_result errors
- Dev/initial scaffold (#38)
- Dev/initial scaffold (#37)
- Dev/initial scaffold (#36)
- Dev/initial scaffold (#35)
- fix: include tool execution results in conversation history (#34)
- fix: include tool execution results in conversation history for subsequent requests
- Merge pull request #32 from agent-panel/dev/initial-scaffold
- fix: prevent model fetch button from overflowing card boundary
- Merge pull request #31 from agent-panel/dev/initial-scaffold
- fix: use correct VersionBug properties (detail/summary) in upgrade dialog
- Merge pull request #28 from agent-panel/dev/initial-scaffold
- fix: revert MinUpgradeVersion back to 0.4.0
- Merge pull request #26 from agent-panel/dev/initial-scaffold
- fix: bump MinUpgradeVersion to 0.5.1 and add API healthcheck

### All Changes

<details><summary>View all</summary>

- Merge pull request #44 from agent-panel/dev/initial-scaffold (86a4b06)
- feat: add version guard for terminate action (min v0.5.2) (2975914)
- feat: add public_ip and connect_ip fields for full agent IP tracking (43307de)
- fix: ensure agent process exits on terminate and add self-cleanup (fefe064)
- feat: add agent terminate action for graceful remote shutdown (b29de70)
- Merge pull request #43 from agent-panel/dev/initial-scaffold (fec2f4a)
- fix: handle timeout field as string or number in run_command (d33dc89)
- Merge pull request #42 from agent-panel/dev/initial-scaffold (89034af)
- fix: ListPendingToolExecutions now includes approved/rejected tools (258365c)
- Merge pull request #41 from agent-panel/dev/initial-scaffold (ea52ec5)
- fix: use total_items instead of items.length for dashboard agent count (ec1d9fd)
- Merge pull request #40 from agent-panel/dev/initial-scaffold (4acc78d)
- fix: prevent long conversation titles from hiding trash button (4b72342)
- Dev/initial scaffold (#39) (d04d72a)
- fix: skip incomplete assistant messages to prevent Claude API tool_result errors (72d52be)
- Dev/initial scaffold (#38) (5d62d3a)
- Merge branch 'main' into dev/initial-scaffold (952df90)
- refactor: move Agent Version and Identifier to Agent Information section (86839a8)
- Dev/initial scaffold (#37) (dc5fe96)
- Dev/initial scaffold (#36) (72d505a)
- feat: reorganize agent detail page with tabbed interface (a061d73)
- Dev/initial scaffold (#35) (5f4c6da)
- Merge branch 'main' into dev/initial-scaffold (89e3a0b)
- refactor: replace swipe with hover delete button for conversations (9280af7)
- debug: add console logs to swipe handlers for debugging (a702405)
- feat: add swipe-to-delete for conversation list items (b1b64df)
- fix: include tool execution results in conversation history (#34) (433d798)
- chore: comment out debug console logs in frontend (fa062e9)
- fix: include tool execution results in conversation history for subsequent requests (2318594)
- feat: add delete conversation functionality across all layers (#33) (fc417cf)
- feat: add delete conversation functionality across all layers (4702fc8)
- Merge pull request #32 from agent-panel/dev/initial-scaffold (295eb8c)
- fix: prevent model fetch button from overflowing card boundary (d0623af)
- Merge pull request #31 from agent-panel/dev/initial-scaffold (d03f5ae)
- fix: use correct VersionBug properties (detail/summary) in upgrade dialog (85d8365)
- Merge pull request #30 from agent-panel/dev/initial-scaffold (87ff4a1)
- refactor: version bug messages include agent version dynamically (9b10263)
- Merge pull request #29 from agent-panel/dev/initial-scaffold (3910b13)
- refactor: replace hasSymlinkBug with extensible getVersionBugs registry (15473e9)
- Merge pull request #28 from agent-panel/dev/initial-scaffold (3a56c18)
- fix: revert MinUpgradeVersion back to 0.4.0 (1e05d83)
- Merge pull request #27 from agent-panel/dev/initial-scaffold (b8c51e3)
- feat: show symlink bug warning in upgrade dialog for agents < v0.5.1 (7815f44)
- Merge pull request #26 from agent-panel/dev/initial-scaffold (34ee185)
- fix: bump MinUpgradeVersion to 0.5.1 and add API healthcheck (6357d06)
</details>

## Quick Install

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash
```
