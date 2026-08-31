---
layout: default
title: Software
permalink: /software
---

# Open Source Software

Grid Coordination develops and publishes open-source libraries that make it practical to build applications using the standards we advocate. All of it is on [GitHub](https://github.com/grid-coordination). Our libraries are MIT licensed. Our public copy of the OpenADR 3 specification is Apache 2.0, and the specification documents in it remain copyright the OpenADR Alliance.

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

The price server is a live deployment of clj-oa3-vtn, composed with a price-fetching layer. It publishes hourly prices of two kinds: dynamic CAISO Day-Ahead Market prices via [GridX](https://www.gridx.com/), and prices computed mathematically from published rate schedules. It also publishes hourly marginal GHG emissions from [SGIP Signal](https://sgipsignal.com/). A client sees hourly price intervals either way, and does not need to know which kind it is reading.

| Service | Endpoint |
|---------|----------|
| REST API base (OpenADR 3.1.0) | `https://price.grid-coordination.energy/openadr3/3.1.0/` |
| Try it in a browser | [`/programs?limit=5`](https://price.grid-coordination.energy/openadr3/3.1.0/programs?limit=5) |
| MQTT push (TLS) | `mqtts://mqtt.grid-coordination.energy:8883` |
| MQTT push (plain) | `mqtt://mqtt.grid-coordination.energy:1883` |
| User guide & tutorials | [price-server-user-guide](https://github.com/grid-coordination/price-server-user-guide) |

No authentication required. About 1,700 programs: PG&E and SCE tariffs across 105 distribution circuits and substations, prices computed directly from published PG&E, SCE, SDG&E, LADWP and City of Palo Alto rate schedules, and hourly marginal GHG emissions for 11 California grid regions. Tutorials available for Python, Clojure, and Rust clients.

## Home Assistant Integration

| Repository | Description |
|------------|-------------|
| [openadr3-ven-hass](https://github.com/grid-coordination/openadr3-ven-hass) | OpenADR 3 VEN integration for Home Assistant — real-time pricing and GHG emissions sensors, MQTT push updates, multi-program support. Available via [HACS](https://hacs.xyz/). [Announcement](https://community.home-assistant.io/t/announcing-openadr-3-ven-for-home-assistant/1005701). |

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

## CEC MIDAS API

Client libraries for the California Energy Commission's [MIDAS](https://www.energy.ca.gov/proceedings/market-informed-demand-automation-server-midas) (Market Informed Demand Automation Server) API.

### Specification

| Repository | Description |
|------------|-------------|
| [midas-api-specs](https://github.com/grid-coordination/midas-api-specs) | Unofficial OpenAPI 3.1 and JSON Schema specifications for the CEC MIDAS API |

### Client Libraries

| Repository | Language | Package |
|------------|----------|---------|
| [clj-midas](https://github.com/grid-coordination/clj-midas) | Clojure | [clj-midas](https://clojars.org/energy.grid-coordination/clj-midas) on Clojars |
| [python-midas](https://github.com/grid-coordination/python-midas) | Python | [python-midas](https://pypi.org/project/python-midas/) on PyPI |

## Emissions &amp; Rate Data

Client libraries for grid emissions and utility rate data services.

| Repository | Language | Description | Package |
|------------|----------|-------------|---------|
| [clj-sgipsignal](https://github.com/grid-coordination/clj-sgipsignal) | Clojure | Client for the [SGIP Signal](https://sgipsignal.com) API — California marginal GHG emissions | [clj-sgipsignal](https://clojars.org/energy.grid-coordination/clj-sgipsignal) on Clojars |
| [clj-watttime](https://github.com/grid-coordination/clj-watttime) | Clojure | Client for the [WattTime](https://watttime.org) API — real-time grid emissions data | [clj-watttime](https://clojars.org/energy.grid-coordination/clj-watttime) on Clojars |
| [clj-urdb](https://github.com/grid-coordination/clj-urdb) | Clojure | Client for the [OpenEI Utility Rate Database](https://openei.org/wiki/Utility_Rate_Database) (URDB) | [clj-urdb](https://clojars.org/energy.grid-coordination/clj-urdb) on Clojars |

## Supporting Libraries

| Repository | Language | Description | Package |
|------------|----------|-------------|---------|
| [clj-mdns](https://github.com/grid-coordination/clj-mdns) | Clojure | mDNS/DNS-SD service discovery | [clj-mdns](https://clojars.org/energy.grid-coordination/clj-mdns) on Clojars |

## Analysis & Proposals

| Repository | Description |
|------------|-------------|
| [caiso-flex-alert](https://github.com/grid-coordination/caiso-flex-alert) | Documentation and analysis of the CAISO Flex Alert API, with an enhancement proposal to support machine-to-machine signalling |

## Architecture

The libraries are designed in layers, each building on the one above it.

![Five stacked layers: OpenAPI specifications, pure API libraries clj-oa3 and python-oa3, client frameworks clj-oa3-client and python-oa3-client, the clj-oa3-vtn server, and applications including the live price server](/images/diagrams/library-layers.svg)

The pure API libraries provide spec-driven HTTP access and data coercion. The client frameworks add lifecycle management, notification channels, and service discovery. The VTN server provides a composable OpenADR 3.1.0 server that can be embedded into larger systems. Applications compose these layers to build grid-coordinated energy management systems.

The Clojure and Python implementations are semantically equivalent, so a team can pick either and get the same behavior.
