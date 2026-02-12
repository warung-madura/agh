---
layout: default
title: Installation Guide
---

# Installation Guide

## One-line Install (Linux / macOS)

```bash
# AgentCtl CLI (no sudo needed)
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install-ctl.sh | bash

# Agent daemon
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | bash

# Agent with config + auto-start (sudo for systemd)
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh \
  | sudo bash -s -- --access-key YOUR_KEY --daemon
```

| Script | Installs | As root | As non-root |
|--------|----------|---------|-------------|
| `install-ctl.sh` | agentctl | `/usr/local/bin` | `~/.local/bin` |
| `install.sh` | agent | `/usr/local/bin` + systemd | `~/.local/bin` + daemon mode |

Scripts automatically detect OS, architecture, and privileges. Checksum is verified when available. `sudo` is only needed for systemd service setup.

## One-line Install (Windows)

> **Note:** PowerShell 5.x defaults to TLS 1.0 which GitHub rejects. The commands below include the TLS 1.2 fix. PowerShell 7+ does not need it.

```powershell
# AgentCtl CLI
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; irm https://github.com/warung-madura/agh/releases/latest/download/install-ctl.ps1 | iex

# Agent daemon
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; irm https://github.com/warung-madura/agh/releases/latest/download/install.ps1 | iex
```

Or download and run the scripts manually:

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

# AgentCtl
Invoke-WebRequest -Uri "https://github.com/warung-madura/agh/releases/latest/download/install-ctl.ps1" -OutFile install-ctl.ps1
.\install-ctl.ps1

# Agent daemon
Invoke-WebRequest -Uri "https://github.com/warung-madura/agh/releases/latest/download/install.ps1" -OutFile install.ps1
.\install.ps1 -AccessKey YOUR_KEY -Daemon
```

| Script | Installs | Default directory | Notes |
|--------|----------|-------------------|-------|
| `install-ctl.ps1` | agentctl | `%LOCALAPPDATA%\AgentPanel` | Per-user, no admin needed |
| `install.ps1` | agent | `%ProgramData%\AgentPanel` | System-wide daemon |

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
   agent -v
   ```

### Windows

1. Download the `.exe` for your platform from the [Downloads](/) page
2. Move it to a folder in your PATH (e.g. `C:\Program Files\AgentPanel\`)
3. Run from PowerShell:
   ```powershell
   .\agent.exe --help
   ```

---

## Agent Usage

### CLI Flags

| Flag | Short | Description |
|------|-------|-------------|
| `--config` | `-c` | Path to config file |
| `--server` | `-s` | WebSocket server URL |
| `--access-key` | `-k` | Access key for authentication |
| `--id` | `-i` | Agent identifier (auto-generated if empty) |
| `--log-level` | `-l` | Log level: debug, info, warn, error |
| `--log-file` | `-f` | Log file path (stdout if empty) |
| `--shell` | `-S` | Default shell for terminal sessions |
| `--version` | `-v` | Show version and exit |
| `--daemon` | `-d` | Run as background daemon |
| `--debug` | `-D` | Enable debug logging |

### Quick Start

```bash
# Connect to server (foreground)
agent -k YOUR_ACCESS_KEY

# Run as background daemon
agent -d -k YOUR_ACCESS_KEY

# With config file
agent -c /etc/agent-panel/config.json

# Daemon with log file
agent -d -c /etc/agent-panel/config.json -f /var/log/agent-panel.log
```

### Environment Variables

| Variable | Description |
|----------|-------------|
| `AGENT_SERVER_URL` | Server URL (overrides config) |
| `AGENT_ACCESS_KEY` | Access key (overrides config) |
| `AGENT_IDENTIFIER` | Agent identifier (overrides config) |
| `AGENT_LOG_LEVEL` | Log level (overrides config) |

### Configuration File

Create `/etc/agent-panel/config.json`:

```json
{
  "access_key": "YOUR_ACCESS_KEY",
  "log_level": "info",
  "enable_files": true,
  "enable_terminal": true,
  "enable_metrics": true
}
```

> `server_url` is optional — the default is baked into the binary at build time. Only set it to override.

---

## AgentCtl Installation

`agentctl` is a CLI for managing agents from your workstation (Windows, macOS, Linux).

### Linux / macOS

```bash
# One-line install (no sudo needed)
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install-ctl.sh | bash

# Or with wget
wget -qO- https://github.com/warung-madura/agh/releases/latest/download/install-ctl.sh | bash

# System-wide (optional)
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install-ctl.sh | sudo bash
```

Or manually:

```bash
# Linux x64
curl -fsSL -o agentctl https://github.com/warung-madura/agh/releases/latest/download/agentctl-linux-amd64

# macOS Apple Silicon
curl -fsSL -o agentctl https://github.com/warung-madura/agh/releases/latest/download/agentctl-darwin-arm64

# macOS Intel
curl -fsSL -o agentctl https://github.com/warung-madura/agh/releases/latest/download/agentctl-darwin-amd64

chmod +x agentctl
sudo mv agentctl /usr/local/bin/
agentctl version
```

### Windows

**Option A — Installer script (recommended):**

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; irm https://github.com/warung-madura/agh/releases/latest/download/install-ctl.ps1 | iex
```

Or download the script first:

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
Invoke-WebRequest -Uri "https://github.com/warung-madura/agh/releases/latest/download/install-ctl.ps1" -OutFile install-ctl.ps1
.\install-ctl.ps1
```

The script auto-detects your architecture, downloads the correct binary, verifies its checksum, installs to `%LOCALAPPDATA%\AgentPanel`, and adds it to your PATH.

**Option B — Manual PowerShell:**

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

# Download
Invoke-WebRequest -Uri "https://github.com/warung-madura/agh/releases/latest/download/agentctl-windows-amd64.exe" -OutFile "$env:USERPROFILE\agentctl.exe"

# Add to PATH (current user, permanent)
$binDir = "$env:USERPROFILE"
$path = [Environment]::GetEnvironmentVariable("PATH", "User")
if ($path -notlike "*$binDir*") {
  [Environment]::SetEnvironmentVariable("PATH", "$path;$binDir", "User")
}

# Verify (open a new terminal first)
agentctl version
```

**Option C — Download manually:**

1. Go to [Releases](https://github.com/warung-madura/agh/releases/latest)
2. Download `agentctl-windows-amd64.exe` (or `arm64` for ARM devices)
3. Rename to `agentctl.exe`
4. Move to a folder in your PATH, or run directly:
   ```powershell
   .\agentctl.exe version
   ```

**Option D — Place in a dedicated folder:**

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

# Create folder
$dir = "$env:LOCALAPPDATA\AgentPanel"
New-Item -ItemType Directory -Force -Path $dir

# Download
Invoke-WebRequest -Uri "https://github.com/warung-madura/agh/releases/latest/download/agentctl-windows-amd64.exe" -OutFile "$dir\agentctl.exe"

# Add folder to user PATH
$path = [Environment]::GetEnvironmentVariable("PATH", "User")
[Environment]::SetEnvironmentVariable("PATH", "$path;$dir", "User")

# Verify (open a new terminal)
agentctl version
```

---

## AgentCtl Usage

### First-time Setup

```bash
# Login — prompts for email and password
agentctl login

# Then you're ready to use all commands
agentctl agents
```

Configuration is saved to `~/.agentctl/config.json` (Linux/macOS) or `%USERPROFILE%\.agentctl\config.json` (Windows).

### Commands

| Command | Description |
|---------|-------------|
| `agentctl login` | Authenticate and select workspace |
| `agentctl agents` | List agents in workspace |
| `agentctl connect <agent>` | Open interactive terminal to agent |
| `agentctl exec <agent> <cmd>` | Execute command on remote agent |
| `agentctl version` | Show version |

### Global Flags

| Flag | Short | Description |
|------|-------|-------------|
| `--server` | `-s` | API server URL (override built-in default) |
| `--config-dir` | | Config directory (default: `~/.agentctl`) |

### Examples

```bash
# List all agents
agentctl agents

# Filter agents by identifier
agentctl agents -i my-server

# Open terminal to an agent
agentctl connect my-server

# Execute a command remotely
agentctl exec my-server "uname -a"

# Execute with timeout and working directory
agentctl exec my-server --timeout 60 --working-dir /var/log "tail -100 syslog"
```

### Windows Examples (PowerShell)

```powershell
# Login
agentctl login

# List agents
agentctl agents

# Connect to terminal
agentctl connect my-server

# Run remote command
agentctl exec my-server "Get-Process | Select-Object -First 10"
```

---

## Running as a Service

### Linux (systemd)

The install script can set this up automatically:

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh \
  | sudo bash -s -- --access-key YOUR_KEY
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
ExecStart=/usr/local/bin/agent -c /etc/agent-panel/config.json
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

### macOS / Linux without systemd

Use the built-in daemon mode:

```bash
agent -d -c /etc/agent-panel/config.json
```

### Windows (NSSM)

1. Download [NSSM](https://nssm.cc/)
2. Open PowerShell as Administrator:
   ```powershell
   nssm install AgentPanel "C:\Program Files\AgentPanel\agent.exe" "-c C:\ProgramData\AgentPanel\config.json"
   nssm set AgentPanel Description "Agent Panel Service"
   nssm set AgentPanel Start SERVICE_AUTO_START
   nssm start AgentPanel
   ```

## Updating

```bash
# Linux / macOS — re-run the matching script
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | bash        # agent
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install-ctl.sh | bash    # agentctl
sudo systemctl restart agent-panel  # if using systemd
```

```powershell
# Windows — re-run the matching installer
.\install.ps1        # agent
.\install-ctl.ps1    # agentctl
```

## Uninstalling

### Linux

```bash
sudo systemctl stop agent-panel
sudo systemctl disable agent-panel
sudo rm /etc/systemd/system/agent-panel.service
sudo systemctl daemon-reload
sudo rm /usr/local/bin/agent /usr/local/bin/agentctl
sudo rm -rf /etc/agent-panel
```

### Windows

```powershell
# Stop service (if using NSSM)
nssm stop AgentPanel
nssm remove AgentPanel confirm

# Remove binaries and config
Remove-Item -Path "$env:LOCALAPPDATA\AgentPanel" -Recurse -Force
Remove-Item -Path "$env:ProgramData\AgentPanel" -Recurse -Force

# Remove from PATH (optional)
$installDir = "$env:LOCALAPPDATA\AgentPanel"
$path = [Environment]::GetEnvironmentVariable("PATH", "User")
$path = ($path.Split(";") | Where-Object { $_ -ne $installDir }) -join ";"
[Environment]::SetEnvironmentVariable("PATH", $path, "User")
```

## Troubleshooting

Enable debug logging:

```bash
agent -D -k YOUR_KEY
```

Check service logs:

```bash
sudo journalctl -u agent-panel -f
```
