---
layout: default
title: Software
permalink: /software
---

# Open Source Software

Grid Coordination develops and publishes open-source libraries that make it practical to build applications using the standards we advocate. All software is MIT licensed and available on [GitHub](https://github.com/grid-coordination).

## Specifications

Machine-readable API specifications that our client libraries are built on:

| Repository | Description |
|------------|-------------|
| [openadr3-specification](https://github.com/grid-coordination/openadr3-specification) | OpenAPI specifications for the [OpenADR 3](https://www.openadr.org/) protocol (versions 3.0.0 through 3.1.1) |
| [gridx-api-specs](https://github.com/grid-coordination/gridx-api-specs) | OpenAPI specifications for GridX pricing APIs, derived from public documentation |

## OpenADR 3 Libraries

Implementations of the OpenADR 3 protocol in Clojure and Python. Each language has a pure API library and a higher-level client framework.

### Pure API Libraries

Spec-driven HTTP clients with full CRUD for all OpenADR 3 resources, two-layer data models (raw JSON and coerced native types), and extensible payload coercion.

| Repository | Language | Package |
|------------|----------|---------|
| [clj-oa3](https://github.com/grid-coordination/clj-oa3) | Clojure | [clj-oa3](https://clojars.org/energy.grid-coordination/clj-oa3) on Clojars |
| [python-oa3](https://github.com/grid-coordination/python-oa3) | Python | [openadr3](https://pypi.org/project/openadr3/) on PyPI |

### Client Frameworks

Higher-level wrappers with lifecycle management, VEN/BL client roles, MQTT and webhook notification channels, and mDNS/DNS-SD service discovery.

| Repository | Language | Package |
|------------|----------|---------|
| [clj-oa3-client](https://github.com/grid-coordination/clj-oa3-client) | Clojure | [clj-oa3-client](https://clojars.org/energy.grid-coordination/clj-oa3-client) on Clojars |
| [python-oa3-client](https://github.com/grid-coordination/python-oa3-client) | Python | [python-oa3-client](https://pypi.org/project/python-oa3-client/) on PyPI |

### Integration Tests

| Repository | Description |
|------------|-------------|
| [clj-oa3-test](https://github.com/grid-coordination/clj-oa3-test) | Integration test suite for OpenADR 3 VTN implementations |

## Other Libraries

| Repository | Language | Description | Package |
|------------|----------|-------------|---------|
| [clj-gridx](https://github.com/grid-coordination/clj-gridx) | Clojure | Client library for the GridX Pricing API | [clj-gridx](https://clojars.org/energy.grid-coordination/clj-gridx) on Clojars |
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
Applications (your code here)
```

The pure API libraries provide spec-driven HTTP access and data coercion. The client frameworks add lifecycle management, notification channels, and service discovery. Applications compose these layers to build grid-coordinated energy management systems.

Both the Clojure and Python implementations follow the same architecture and provide semantically equivalent functionality, so teams can choose the language that fits their stack.
