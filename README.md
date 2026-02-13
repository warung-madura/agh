# Agent Panel

Latest: [v0.5.3](https://github.com/warung-madura/agh/releases/tag/v0.5.3)

## Install Agent (Linux / macOS)

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh | bash
```

Install + configure + auto-start (sudo for systemd):

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install.sh \
  | sudo bash -s -- --access-key YOUR_KEY --daemon
```

## Install AgentCtl

### Linux / macOS

```bash
curl -sSL https://github.com/warung-madura/agh/releases/latest/download/install-ctl.sh | bash
```

### Windows (PowerShell)

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; irm https://github.com/warung-madura/agh/releases/latest/download/install-ctl.ps1 | iex
```

### Manual Download

Download from the [releases page](https://github.com/warung-madura/agh/releases/latest):
- **Windows x64**: `agentctl-windows-amd64.exe`
- **Windows ARM64**: `agentctl-windows-arm64.exe`
- **Linux x64**: `agentctl-linux-amd64`
- **macOS Apple Silicon**: `agentctl-darwin-arm64`
- **macOS Intel**: `agentctl-darwin-amd64`

## Usage

```bash
# Agent — run as daemon
agent -d -k YOUR_ACCESS_KEY

# AgentCtl — login and manage
agentctl login
agentctl agents
agentctl connect my-server
agentctl exec my-server "uname -a"
```

## Documentation

- [Downloads](https://warung-madura.github.io/agh)
- [Installation Guide](https://warung-madura.github.io/agh/install)
- [Changelog](https://warung-madura.github.io/agh/changelog)
