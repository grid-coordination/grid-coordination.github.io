---
layout: default
title: Software
permalink: /software
---

# Open Source Software

Grid Coordination develops and publishes open-source libraries that make it practical to build applications using the standards we advocate. All software is MIT licensed and available on [GitHub](https://github.com/grid-coordination).

## OpenADR 3 Libraries

Implementations of the [OpenADR 3](https://www.openadr.org/) protocol in Clojure and Python. Each language has a pure API library and a higher-level client framework.

### Specification

| Repository | Description |
|------------|-------------|
| [openadr3-specification](https://github.com/grid-coordination/openadr3-specification) | OpenAPI specifications for the OpenADR 3 protocol (versions 3.0.0 through 3.1.1) |

Each language has a two-layer stack: a **pure API library** (spec-driven HTTP client with full CRUD, two-layer data models, extensible payload coercion) and a **client framework** (lifecycle management, VEN/BL client roles, MQTT and webhook notification channels, mDNS/DNS-SD service discovery).

### Clojure

| Repository | Layer | Package |
|------------|-------|---------|
| [clj-oa3](https://github.com/grid-coordination/clj-oa3) | Pure API | [clj-oa3](https://clojars.org/energy.grid-coordination/clj-oa3) on Clojars |
| [clj-oa3-client](https://github.com/grid-coordination/clj-oa3-client) | Client framework | [clj-oa3-client](https://clojars.org/energy.grid-coordination/clj-oa3-client) on Clojars |
| [clj-oa3-test](https://github.com/grid-coordination/clj-oa3-test) | Integration tests for VTN implementations | &mdash; |

### Python

| Repository | Layer | Package |
|------------|-------|---------|
| [python-oa3](https://github.com/grid-coordination/python-oa3) | Pure API | [openadr3](https://pypi.org/project/openadr3/) on PyPI |
| [python-oa3-client](https://github.com/grid-coordination/python-oa3-client) | Client framework | [python-oa3-client](https://pypi.org/project/python-oa3-client/) on PyPI |

### VTN Server

| Repository | Description | Package |
|------------|-------------|---------|
| [clj-oa3-vtn](https://github.com/grid-coordination/clj-oa3-vtn) | OpenADR 3.1.0 VTN server with BL/VEN two-port architecture, MQTT notifications, pluggable storage | [clj-oa3-vtn](https://clojars.org/energy.grid-coordination/clj-oa3-vtn) on Clojars |

## Live Services

The price server is a live deployment of clj-oa3-vtn, composed with a price-fetching layer that serves hourly California marginal electricity prices from the CAISO Day-Ahead Market via [GridX](https://www.gridx.com/).

| Service | Endpoint |
|---------|----------|
| REST API (OpenADR 3.1.0) | [price.grid-coordination.energy](https://price.grid-coordination.energy/openadr3/3.1.0/) |
| MQTT push (TLS) | `mqtts://mqtt.grid-coordination.energy:8883` |
| MQTT push (plain) | `tcp://mqtt.grid-coordination.energy:1883` |
| User guide & tutorials | [price-server-user-guide](https://github.com/grid-coordination/price-server-user-guide) |

No authentication required. 492 programs covering PG&E and SCE tariffs across 105 distribution circuits and substations. Tutorials available for Python, Clojure, and Rust clients.

## GridX Pricing API

Client library for the GridX dynamic pricing API.

### Specification

| Repository | Description |
|------------|-------------|
| [gridx-api-specs](https://github.com/grid-coordination/gridx-api-specs) | OpenAPI specifications for GridX pricing APIs, derived from public documentation |

### Client Library

| Repository | Language | Package |
|------------|----------|---------|
| [clj-gridx](https://github.com/grid-coordination/clj-gridx) | Clojure | [clj-gridx](https://clojars.org/energy.grid-coordination/clj-gridx) on Clojars |

## Supporting Libraries

| Repository | Language | Description | Package |
|------------|----------|-------------|---------|
| [clj-mdns](https://github.com/grid-coordination/clj-mdns) | Clojure | mDNS/DNS-SD service discovery | [clj-mdns](https://clojars.org/energy.grid-coordination/clj-mdns) on Clojars |

## Architecture

The libraries are designed in layers:

```
Specifications (OpenAPI YAML)
  |
Pure API libraries (clj-oa3, python-oa3)
  |
Client frameworks (clj-oa3-client, python-oa3-client)
  |
VTN server (clj-oa3-vtn)
  |
Applications & live services (price server, your code here)
```

The pure API libraries provide spec-driven HTTP access and data coercion. The client frameworks add lifecycle management, notification channels, and service discovery. The VTN server provides a composable OpenADR 3.1.0 server that can be embedded into larger systems. Applications compose these layers to build grid-coordinated energy management systems.

Both the Clojure and Python implementations follow the same architecture and provide semantically equivalent functionality, so teams can choose the language that fits their stack.
