---
layout: default
title: Changelog
---

## Agent Panel v0.2.0

Released on 2026-02-12

### New Features

- feat: replace playbooks with saved prompts, add access key reveal, fix safety mode
- feat: add per-workspace safety mode and fix assistant streaming bugs
- fix: harden billing system against subscription manipulation
- feat: add reveal toggle for generated access key
- Merge pull request #2 from agent-panel/dev/initial-scaffold
- feat: add DB/Redis health checks and improve Dockerfile
- feat: add production docker-compose, trusted proxy support, and CI cleanup

### Bug Fixes

- feat: replace playbooks with saved prompts, add access key reveal, fix safety mode
- feat: add per-workspace safety mode and fix assistant streaming bugs
- fix: harden billing system against subscription manipulation
- fix: parse comma-separated CORS origins from env var
- fix: refactor CORS to configurable struct and fix assistant chat overflow
- fix: update default server URL from api.loader.id to connect.debian.so
- fix: CORS middleware now handles wildcard * origin correctly
- fix: handle empty REDIS_PASSWORD in docker-compose
- Merge pull request #3 from agent-panel/dev/initial-scaffold
- fix: remove unused isOwner variable in members page
- Merge pull request #1 from agent-panel/dev/initial-scaffold
- fix: change access key prefix from agp_ to agh_

### All Changes

<details><summary>View all</summary>

- Merge pull request #6 from agent-panel/dev/initial-scaffold (8808616)
- feat: replace playbooks with saved prompts, add access key reveal, fix safety mode (22da547)
- feat: add per-workspace safety mode and fix assistant streaming bugs (80a7ae3)
- fix: harden billing system against subscription manipulation (8c61fa9)
- feat: add reveal toggle for generated access key (0879cd4)
- Merge pull request #5 from agent-panel/dev/initial-scaffold (03dd90d)
- chore: remove hardcoded cors_origins from config.yaml (14849d0)
- fix: parse comma-separated CORS origins from env var (29b83b3)
- fix: refactor CORS to configurable struct and fix assistant chat overflow (d8b08eb)
- fix: update default server URL from api.loader.id to connect.debian.so (517bf32)
- Merge pull request #4 from agent-panel/dev/initial-scaffold (6b35563)
- fix: CORS middleware now handles wildcard * origin correctly (e892e05)
- fix: handle empty REDIS_PASSWORD in docker-compose (68666fb)
- Merge pull request #3 from agent-panel/dev/initial-scaffold (6508539)
- fix: remove unused isOwner variable in members page (79b0baf)
- Merge pull request #2 from agent-panel/dev/initial-scaffold (89e52c1)
- feat: add DB/Redis health checks and improve Dockerfile (0dac154)
- Merge pull request #1 from agent-panel/dev/initial-scaffold (dadb033)
- fix: change access key prefix from agp_ to agh_ (72f854a)
- feat: add production docker-compose, trusted proxy support, and CI cleanup (1efee28)
</details>

## Quick Install

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash
```
