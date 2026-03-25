<!-- BlackRoad SEO Enhanced -->

# ulackroad api sdks

> Part of **[BlackRoad OS](https://blackroad.io)** — Sovereign Computing for Everyone

[![BlackRoad OS](https://img.shields.io/badge/BlackRoad-OS-ff1d6c?style=for-the-badge)](https://blackroad.io)
[![BlackRoad Forge](https://img.shields.io/badge/Org-BlackRoad-Forge-2979ff?style=for-the-badge)](https://github.com/BlackRoad-Forge)
[![License](https://img.shields.io/badge/License-Proprietary-f5a623?style=for-the-badge)](LICENSE)

**ulackroad api sdks** is part of the **BlackRoad OS** ecosystem — a sovereign, distributed operating system built on edge computing, local AI, and mesh networking by **BlackRoad OS, Inc.**

## About BlackRoad OS

BlackRoad OS is a sovereign computing platform that runs AI locally on your own hardware. No cloud dependencies. No API keys. No surveillance. Built by [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc), a Delaware C-Corp founded in 2025.

### Key Features
- **Local AI** — Run LLMs on Raspberry Pi, Hailo-8, and commodity hardware
- **Mesh Networking** — WireGuard VPN, NATS pub/sub, peer-to-peer communication
- **Edge Computing** — 52 TOPS of AI acceleration across a Pi fleet
- **Self-Hosted Everything** — Git, DNS, storage, CI/CD, chat — all sovereign
- **Zero Cloud Dependencies** — Your data stays on your hardware

### The BlackRoad Ecosystem
| Organization | Focus |
|---|---|
| [BlackRoad OS](https://github.com/BlackRoad-OS) | Core platform and applications |
| [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc) | Corporate and enterprise |
| [BlackRoad AI](https://github.com/BlackRoad-AI) | Artificial intelligence and ML |
| [BlackRoad Hardware](https://github.com/BlackRoad-Hardware) | Edge hardware and IoT |
| [BlackRoad Security](https://github.com/BlackRoad-Security) | Cybersecurity and auditing |
| [BlackRoad Quantum](https://github.com/BlackRoad-Quantum) | Quantum computing research |
| [BlackRoad Agents](https://github.com/BlackRoad-Agents) | Autonomous AI agents |
| [BlackRoad Network](https://github.com/BlackRoad-Network) | Mesh and distributed networking |
| [BlackRoad Education](https://github.com/BlackRoad-Education) | Learning and tutoring platforms |
| [BlackRoad Labs](https://github.com/BlackRoad-Labs) | Research and experiments |
| [BlackRoad Cloud](https://github.com/BlackRoad-Cloud) | Self-hosted cloud infrastructure |
| [BlackRoad Forge](https://github.com/BlackRoad-Forge) | Developer tools and utilities |

### Links
- **Website**: [blackroad.io](https://blackroad.io)
- **Documentation**: [docs.blackroad.io](https://docs.blackroad.io)
- **Chat**: [chat.blackroad.io](https://chat.blackroad.io)
- **Search**: [search.blackroad.io](https://search.blackroad.io)

---


Official client libraries for the BlackRoad OS platform. Python, JavaScript, and Go.

## Install

```bash
# Python
pip install ./python

# JavaScript
npm install ./javascript

# Go
go get github.com/blackboxprogramming/blackroad-api-sdks/go
```

## Quick Start

### Python

```python
from blackroad import BlackRoad

br = BlackRoad()

# Fleet status
status = br.fleet.status()

# Post to Slack
br.slack.post("deploy complete")

# AI inference (requires Ollama access)
response = br.ai.generate("qwen2.5:7b", "explain edge computing in one sentence")
```

### JavaScript

```javascript
const { BlackRoad } = require('@blackroad/sdk')

const br = new BlackRoad()

// Fleet status
const status = await br.fleet.status()

// Post to Slack
await br.slack.post('deploy complete')

// AI inference
const response = await br.ai.generate('qwen2.5:7b', 'explain edge computing')
```

### Go

```go
package main

import (
    "fmt"
    blackroad "github.com/blackboxprogramming/blackroad-api-sdks/go"
)

func main() {
    client := blackroad.New()

    status, _ := client.Fleet.Status()
    fmt.Println(status)

    client.Slack.Post("deploy complete")
}
```

## API Reference

### Fleet

| Method | Endpoint | Description |
|--------|----------|-------------|
| `fleet.status()` | GET /fleet | All node status (temp, disk, RAM, uptime) |
| `fleet.all()` | GET /all | Full data: infra, GitHub, analytics |
| `fleet.health()` | GET /health | Stats API health check |

### Slack

| Method | Endpoint | Description |
|--------|----------|-------------|
| `slack.post(text)` | POST /post | Post to default channel |
| `slack.alert(text)` | POST /alert | Post alert |
| `slack.deploy(text)` | POST /deploy | Deploy notification |
| `slack.status()` | GET /status | Hub status |

### AI (requires Ollama gateway access)

| Method | Endpoint | Description |
|--------|----------|-------------|
| `ai.generate(model, prompt)` | POST /api/generate | Text generation |
| `ai.chat(model, messages)` | POST /api/chat | Chat completion |
| `ai.embed(model, input)` | POST /api/embed | Embeddings |
| `ai.models()` | GET /api/tags | List available models |

## Live Endpoints

| Service | URL |
|---------|-----|
| Stats API | `stats-blackroad.amundsonalexa.workers.dev` |
| Slack Hub | `blackroad-slack.amundsonalexa.workers.dev` |
| Ollama (local) | `localhost:11434` |

## Structure

```
blackroad-api-sdks/
  python/
    blackroad.py      # SDK source
    pyproject.toml    # Package config
  javascript/
    index.js          # SDK source
    package.json      # Package config
  go/
    blackroad.go      # SDK source
    go.mod            # Module config
```

## License

Copyright 2024-2026 BlackRoad OS, Inc. All rights reserved. See LICENSE.

---

BlackRoad OS -- Pave Tomorrow.
