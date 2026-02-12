---
layout: default
title: Changelog
---

## Agent Panel v0.5.0

Released on 2026-02-12

### New Features

- Merge pull request #24 from agent-panel/dev/initial-scaffold
- feat: extend agent system info with network, user, environment details
- Merge pull request #23 from agent-panel/dev/initial-scaffold
- feat: add symlink icons and is_symlink field to file explorer
- Merge pull request #22 from agent-panel/dev/initial-scaffold
- feat: add sortable columns to file explorer (dirs first, name/size/date)
- Merge pull request #20 from agent-panel/dev/initial-scaffold
- feat: add CodeMirror shell editor for saved commands and ignore nul artifacts
- Merge pull request #19 from agent-panel/dev/initial-scaffold
- feat: add saved terminal commands with Sheet UI for quick access
- feat: add recommended labels to model selection dropdown
- feat: add fetch models from AI provider with searchable combobox
- feat: add response language setting to AI persona configuration
- feat: plan-based AI tool iteration limits per workspace subscription
- feat: add smart timeout support for AI command execution
- feat: show thinking indicator while waiting for AI response
- feat: add AI persona mode per workspace with custom instructions
- feat: simplify AI tools to single run_command with OS-adaptive prompt and improved output
- Merge pull request #10 from agent-panel/dev/initial-scaffold
- feat: add step-by-step setup guide for agents page empty state
- Merge pull request #9 from agent-panel/dev/initial-scaffold
- feat: add version guard for agent remote upgrade (minimum v0.4.0)
- feat: add branding, marketing, upgrade prompts, and workspace improvements
- feat: improve workspace switcher with create dialog, UX enhancements, and error handling

### Bug Fixes

- fix: configure Vite HMR for devcontainer compatibility
- fix: remove unused useMemo import and update go.work.sum
- Merge pull request #21 from agent-panel/dev/initial-scaffold
- fix: enable line wrapping in CodeMirror command editor
- fix: tell AI the user owns the server for proper authority context
- fix: improve AI system prompt to use simple commands instead of complex pipelines
- fix: restore chat message scrolling with proper overflow constraints
- fix: make conversation history sidebar sticky in assistant page
- Merge pull request #15 from agent-panel/dev/initial-scaffold
- fix: prevent browser window scrolling on assistant chat page
- Merge pull request #14 from agent-panel/dev/initial-scaffold
- fix: cascade delete conversations when agent is deleted
- fix: resolve SSE streaming errors behind Cloudflare and fix chat display bugs
- fix: use stored API key when testing AI connection without key in request
- fix: persist auto-executed tool calls and remove overly broad query invalidation
- feat: simplify AI tools to single run_command with OS-adaptive prompt and improved output

### All Changes

<details><summary>View all</summary>

- Merge pull request #24 from agent-panel/dev/initial-scaffold (029164e)
- fix: configure Vite HMR for devcontainer compatibility (11f297c)
- fix: remove unused useMemo import and update go.work.sum (3959270)
- feat: extend agent system info with network, user, environment details (c1f7cc3)
- Merge pull request #23 from agent-panel/dev/initial-scaffold (1efd16b)
- feat: add symlink icons and is_symlink field to file explorer (434a706)
- Merge pull request #22 from agent-panel/dev/initial-scaffold (fb7ebc8)
- feat: add sortable columns to file explorer (dirs first, name/size/date) (d48b62d)
- Merge pull request #21 from agent-panel/dev/initial-scaffold (f6769a9)
- fix: enable line wrapping in CodeMirror command editor (f4d4388)
- Merge pull request #20 from agent-panel/dev/initial-scaffold (0919366)
- feat: add CodeMirror shell editor for saved commands and ignore nul artifacts (4f09eec)
- Merge pull request #19 from agent-panel/dev/initial-scaffold (d07fe8a)
- feat: add saved terminal commands with Sheet UI for quick access (8e2f05c)
- Merge pull request #18 from agent-panel/dev/initial-scaffold (88e2301)
- feat: add recommended labels to model selection dropdown (70b72a9)
- feat: add fetch models from AI provider with searchable combobox (1f7ba0f)
- feat: add response language setting to AI persona configuration (6c61162)
- feat: plan-based AI tool iteration limits per workspace subscription (a8e62ca)
- Merge pull request #17 from agent-panel/dev/initial-scaffold (e8f9a4b)
- fix: tell AI the user owns the server for proper authority context (69db3a5)
- fix: improve AI system prompt to use simple commands instead of complex pipelines (5ac3f8d)
- Merge branch 'dev/initial-scaffold' (05444a6)
- fix: restore chat message scrolling with proper overflow constraints (9c1c54d)
- Merge pull request #16 from agent-panel/dev/initial-scaffold (12b69ea)
- feat: add smart timeout support for AI command execution (93d425d)
- feat: show thinking indicator while waiting for AI response (66220e4)
- fix: make conversation history sidebar sticky in assistant page (e37a349)
- Merge pull request #15 from agent-panel/dev/initial-scaffold (7711c51)
- fix: prevent browser window scrolling on assistant chat page (5711323)
- Merge pull request #14 from agent-panel/dev/initial-scaffold (3e9b90d)
- fix: cascade delete conversations when agent is deleted (e87a0a5)
- Merge pull request #13 from agent-panel/dev/initial-scaffold (d60c5a0)
- refactor: rename playbooks to saved-prompts for consistency (b1b94d0)
- fix: resolve SSE streaming errors behind Cloudflare and fix chat display bugs (43d3c94)
- Merge pull request #12 from agent-panel/dev/initial-scaffold (7483911)
- fix: use stored API key when testing AI connection without key in request (495b32e)
- fix: persist auto-executed tool calls and remove overly broad query invalidation (ea1871b)
- Merge pull request #11 from agent-panel/dev/initial-scaffold (7fe2122)
- feat: add AI persona mode per workspace with custom instructions (7bccee0)
- feat: simplify AI tools to single run_command with OS-adaptive prompt and improved output (32cc5af)
- Merge pull request #10 from agent-panel/dev/initial-scaffold (19f22dd)
- feat: add step-by-step setup guide for agents page empty state (a4a1c32)
- Merge pull request #9 from agent-panel/dev/initial-scaffold (62a8f1a)
- feat: add version guard for agent remote upgrade (minimum v0.4.0) (f7f920f)
- Merge pull request #8 from agent-panel/dev/initial-scaffold (a422fa4)
- feat: add branding, marketing, upgrade prompts, and workspace improvements (2df9ca6)
- feat: improve workspace switcher with create dialog, UX enhancements, and error handling (5e7b20a)
</details>

## Quick Install

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash
```
