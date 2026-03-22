# RRBR — rrbr-api

> **API Gateway**: gRPC and REST service contracts for inter-service communication.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

## Overview

Central API gateway and Protobuf contract definitions for the RRBR system. All services communicate through typed, versioned contracts defined here.

## Stack

- **Protobuf 3** — service contract definitions (source of truth)
- **gRPC** — internal service communication (engine ↔ agents ↔ data)
- **REST/OpenAPI** — external-facing API for frontend and third-party integrations
- **Python / Go** — gateway implementation

## Contract Structure

```
proto/
├── quant/
│   ├── pricing.proto      # Pricing requests/responses per product
│   ├── risk.proto         # Risk metrics (DV01, Greeks, FRTB charges)
│   └── curves.proto       # Curve construction and queries
├── agents/
│   ├── supervisor.proto   # Agent task dispatch
│   └── explain.proto      # Explanation requests
└── data/
    ├── market_data.proto  # Market data feed
    └── trades.proto       # Trade events
```

## License

Apache 2.0
