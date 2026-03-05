[![CI](https://github.com/blackboxprogramming/blackroad-api-sdks/actions/workflows/ci.yml/badge.svg)](https://github.com/blackboxprogramming/blackroad-api-sdks/actions/workflows/ci.yml)
[![Security Scan](https://github.com/blackboxprogramming/blackroad-api-sdks/actions/workflows/security-scan.yml/badge.svg)](https://github.com/blackboxprogramming/blackroad-api-sdks/actions/workflows/security-scan.yml)
[![Auto Deploy](https://github.com/blackboxprogramming/blackroad-api-sdks/actions/workflows/auto-deploy.yml/badge.svg)](https://github.com/blackboxprogramming/blackroad-api-sdks/actions/workflows/auto-deploy.yml)
[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-red.svg)](LICENSE)

# BlackRoad API SDKs

Official SDKs for the BlackRoad API. Available in JavaScript/TypeScript, Python, Go, and Ruby.

> **Proprietary Software** - Copyright 2024-2026 BlackRoad OS, Inc. All Rights Reserved. See [LICENSE](LICENSE) for details.

## Supported Languages

| Language | File | Status |
|----------|------|--------|
| JavaScript/TypeScript | [`javascript-sdk.ts`](javascript-sdk.ts) | Production |
| Python | [`python-sdk.py`](python-sdk.py) | Production |
| Go | [`go-sdk.go`](go-sdk.go) | Production |
| Ruby | [`ruby-sdk.rb`](ruby-sdk.rb) | Production |

## Quick Start

### JavaScript/TypeScript

```typescript
import { BlackRoad } from '@blackroad/sdk';

const client = new BlackRoad({ apiKey: 'your-api-key' });

// List products
const products = await client.products.list();

// Create a deployment
const deployment = await client.deployments.create('product-123', 'production');

// Check deployment status
const status = await client.deployments.getStatus(deployment.id);
```

### Python

```python
from blackroad import BlackRoad

client = BlackRoad(api_key="your-api-key")

# List products
products = client.products.list()

# Create a deployment
deployment = client.deployments.create(
    product_id="product-123",
    environment="production"
)

# Check deployment status
status = client.deployments.get_status(deployment["id"])
```

### Go

```go
package main

import (
    blackroad "github.com/blackboxprogramming/blackroad-api-sdks"
)

func main() {
    client := blackroad.NewClient("your-api-key")

    // List products
    products, err := client.ListProducts(100)

    // Create a deployment
    deployment, err := client.CreateDeployment("product-123", "production")

    // Check deployment status
    status, err := client.GetDeploymentStatus(deployment.ID)
}
```

### Ruby

```ruby
require_relative 'ruby-sdk'

client = BlackRoad::Client.new(api_key: 'your-api-key')

# List products
products = client.products.list

# Create a deployment
deployment = client.deployments.create(
  product_id: 'product-123',
  environment: 'production'
)

# Check deployment status
status = client.deployments.get_status(deployment['id'])
```

## API Reference

**Base URL:** `https://api.blackroad.io`

### Authentication

All requests require a Bearer token in the `Authorization` header:

```
Authorization: Bearer your-api-key
```

### Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/v1/products` | List all products |
| `GET` | `/v1/products/:id` | Get product by ID |
| `POST` | `/v1/products` | Create a product |
| `GET` | `/v1/deployments` | List all deployments |
| `POST` | `/v1/deployments` | Create a deployment |
| `GET` | `/v1/deployments/:id` | Get deployment status |
| `GET` | `/v1/analytics` | Get analytics data |

## Infrastructure

- **CI/CD**: GitHub Actions (pinned to commit hashes)
- **Hosting**: Cloudflare Pages / Cloudflare Workers
- **Backend**: Railway
- **Security**: CodeQL analysis, dependency scanning, Dependabot
- **Monitoring**: Self-healing workflow with auto-rollback
- **Payments**: Stripe (product and subscription management)

## Workflows

| Workflow | Trigger | Description |
|----------|---------|-------------|
| CI | Push, PR | Validates all SDKs (syntax, lint, vet) |
| Auto Deploy | Push to main | Deploys to Cloudflare or Railway |
| Security Scan | Push, PR, Weekly | CodeQL + dependency scanning |
| Self-Healing | Every 6h, post-deploy | Health monitoring + auto-rollback |
| Cloudflare Workers | Push (workers/) | Deploys Cloudflare Workers |
| Automerge | Dependabot PRs | Auto-merges patch/minor updates |

## License

Proprietary BlackRoad OS, Inc. License. All Rights Reserved. This software is not open source. See [LICENSE](LICENSE) for full terms.

---

BlackRoad OS, Inc.
