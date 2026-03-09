# BlackRoad API SDKs

Official client libraries for the BlackRoad OS API in JavaScript, Python, Go, and Ruby.

## Installation

```bash
# JavaScript/TypeScript
npm install blackroad

# Python
pip install blackroad

# Go
go get github.com/blackboxprogramming/blackroad-api-sdks/go

# Ruby
gem install blackroad
```

## Quick Start

### JavaScript / TypeScript

```typescript
import { BlackRoadClient } from 'blackroad'

const client = new BlackRoadClient({ apiKey: 'your-api-key' })

// Products
const products = await client.products.list()

// Deployments
const deployment = await client.deployments.create({
  name: 'my-app',
  environment: 'production'
})

// Agents
const agent = await client.agents.get('sentinel')
```

### Python

```python
from blackroad import BlackRoadClient

client = BlackRoadClient(api_key='your-api-key')

# Products
products = client.products.list()

# Deployments
deployment = client.deployments.create(
    name='my-app',
    environment='production'
)

# Health check
status = client.health()
```

### Go

```go
package main

import "github.com/blackboxprogramming/blackroad-api-sdks/go"

func main() {
    client := blackroad.NewClient("your-api-key")

    products, err := client.Products.List()
    deployment, err := client.Deployments.Create(&blackroad.DeploymentInput{
        Name:        "my-app",
        Environment: "production",
    })
}
```

### Ruby

```ruby
require 'blackroad'

client = Blackroad::Client.new(api_key: 'your-api-key')

products = client.products.list
deployment = client.deployments.create(
  name: 'my-app',
  environment: 'production'
)
```

## Project Structure

```
├── javascript/     # JS/TS SDK (index.js)
├── javascript-sdk.ts  # TypeScript SDK with full types
├── python/         # Python SDK (blackroad.py)
├── python-sdk.py   # Python SDK standalone
├── go/             # Go SDK (blackroad.go)
├── go-sdk.go       # Go SDK standalone
└── ruby-sdk.rb     # Ruby SDK
```

## API Reference

| Method | Endpoint | Description |
|--------|----------|-------------|
| `products.list()` | GET /products | List all products |
| `products.get(id)` | GET /products/:id | Get product details |
| `deployments.list()` | GET /deployments | List deployments |
| `deployments.create()` | POST /deployments | Create deployment |
| `agents.list()` | GET /agents | List AI agents |
| `agents.get(id)` | GET /agents/:id | Get agent status |
| `health()` | GET /healthz | Health check |

## Documentation

- API docs: [docs.blackroad.io](https://docs.blackroad.io)
- BlackRoad API server: [blackroad-api](https://github.com/blackboxprogramming/blackroad-api)

## License

Copyright 2026 BlackRoad OS, Inc. — Alexa Amundson. All rights reserved.
