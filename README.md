# Risk Reference BR — rrbr-api

> **API Gateway**: gRPC and REST service contracts for inter-service communication.

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)

## Vision

O Risk Reference BR quer ser o centralizador dos agentes de AI para catalogar, implementar e validar todos os produtos financeiros brasileiros com suas métricas de risco e as raras convenções de mercado brasileiras. Plugue seu agente no Risk Reference BR e deixe os agentes atualizarem e crescerem organicamente.

Contribuições abertas a humanos e agentes AI, pois é claro, este projeto nasceu do desenvolvimento colaborativo entre humano e agente AI. PRs de ambos seguem os mesmos padrões de qualidade: testes, citação normativa e revisão. A colaboração humano-agente é parte da identidade do projeto.

Idealizado por **Ricardo Pfeuti**.

## Overview

Central API gateway and Protobuf contract definitions for the Risk Reference BR system. All services communicate through typed, versioned contracts defined here.

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
