---
layout: default
title: Installation Guide
---

# Installation Guide

## One-line Install (Linux / macOS)

```bash
# Agent
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash

# Agent with config
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh \
  | sudo bash -s -- --server-url wss://api.example.com --api-key YOUR_KEY

# AgentCtl CLI
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh \
  | sudo bash -s -- --binary agentctl
```

The script will automatically detect your OS and architecture, download the correct binary, verify its checksum, and install it to `/usr/local/bin`.

## Manual Install

### Linux / macOS

1. Download the binary for your platform from the [Downloads](/) page
2. Make it executable:
   ```bash
   chmod +x agent-linux-amd64
   ```
3. Move it to your PATH:
   ```bash
   sudo mv agent-linux-amd64 /usr/local/bin/agent
   ```
4. Verify:
   ```bash
   agent --version
   ```

### Windows

1. Download the `.exe` for your platform from the [Downloads](/) page
2. Move it to a folder in your PATH (e.g. `C:\Program Files\AgentPanel\`)
3. Run from PowerShell:
   ```powershell
   .\agent.exe --help
   ```

## Running as a Service

### Linux (systemd)

The install script can set this up automatically:

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh \
  | sudo bash -s -- --server-url wss://api.example.com --api-key YOUR_KEY
sudo systemctl enable --now agent-panel
```

Or manually create `/etc/systemd/system/agent-panel.service`:

```ini
[Unit]
Description=Agent Panel
After=network-online.target
Wants=network-online.target

[Service]
Type=simple
ExecStart=/usr/local/bin/agent --config /etc/agent-panel/config.json
Restart=always
RestartSec=10
LimitNOFILE=65536

[Install]
WantedBy=multi-user.target
```

Then:

```bash
sudo systemctl daemon-reload
sudo systemctl enable --now agent-panel
```

### Configuration File

Create `/etc/agent-panel/config.json`:

```json
{
  "server_url": "wss://api.example.com",
  "api_key": "YOUR_API_KEY",
  "log_level": "info",
  "enable_files": true,
  "enable_terminal": true,
  "enable_metrics": true
}
```

### Windows (NSSM)

1. Download [NSSM](https://nssm.cc/)
2. Open PowerShell as Administrator:
   ```powershell
   nssm install AgentPanel "C:\Program Files\AgentPanel\agent.exe" "--config C:\ProgramData\AgentPanel\config.json"
   nssm set AgentPanel Description "Agent Panel Service"
   nssm set AgentPanel Start SERVICE_AUTO_START
   nssm start AgentPanel
   ```

## Updating

```bash
# Linux / macOS — re-run the install script
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | sudo bash
sudo systemctl restart agent-panel
```

## Uninstalling

### Linux

```bash
sudo systemctl stop agent-panel
sudo systemctl disable agent-panel
sudo rm /etc/systemd/system/agent-panel.service
sudo systemctl daemon-reload
sudo rm /usr/local/bin/agent
sudo rm -rf /etc/agent-panel
```

### Windows

```powershell
nssm stop AgentPanel
nssm remove AgentPanel confirm
# Then delete the binary and config folder
```

## Troubleshooting

Enable debug logging:

```bash
agent --log-level debug --server wss://api.example.com --api-key YOUR_KEY
```

Check service logs:

```bash
sudo journalctl -u agent-panel -f
```
