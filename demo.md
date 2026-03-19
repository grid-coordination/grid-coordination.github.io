---
layout: default
title: Live Demo
permalink: /demo
---

# Price-based Demand Flexibility with OpenADR 3

At the [2025 California Demand Flexibility Summit](https://www.energy.ca.gov/event/meeting/2025-05/2025-california-demand-flexibility-summit), hosted by the California Energy Commission, we demonstrated a complete grid-to-appliance coordination system using OpenADR 3, open-source software, and inexpensive hardware.

The demo showed what we've been advocating: **dynamic pricing delivered over open protocols, driving autonomous local optimization of household loads.** Not a simulation — a working system.

## What We Built

A grid price server communicates hourly dynamic prices via [OpenADR 3](https://www.openadr.org/) to a customer gateway, which then distributes those prices over the local network to mock appliances — an EV charger, water heater, and HVAC system. Each appliance independently optimizes its behavior based on the current and forecast price.

### The Architecture

```
Cloud                        Customer Home (LAN)
┌──────────────┐             ┌────────────────────────────────┐
│ Grid Price   │  OpenADR 3  │  Gateway / HEMS                │
│ Server (VTN) │────────────>│  (Home Assistant + OpenADR VEN) │
└──────────────┘             │         │                      │
                             │    OpenADR 3 (local)           │
                             │    ┌────┴─────┬───────┐        │
                             │    v          v       v        │
                             │  EV Charger  WH    HVAC       │
                             └────────────────────────────────┘
```

- The **gateway** receives prices from the cloud and re-publishes them locally
- Each **appliance** discovers the gateway automatically via mDNS and connects
- Appliances respond to price signals autonomously — no aggregator, no proprietary cloud

### How Appliances Use Prices

Each load optimizes against the current price and forecast. The demo used a simple algorithm for illustration — real products would be more sophisticated, optimizing across many hours using thermal storage (water heater), electrical storage (battery), or deferred service delivery (pool pump, EV charging).

When the price is low, deferrable loads run. When the price spikes, they curtail. The gateway computes an effective **local price** that accounts for self-generation and storage, so appliances always see the most relevant signal.

## Hardware

| Component | Hardware | Cost |
|-----------|----------|------|
| Gateway | Raspberry Pi 4 | ~$35 |
| Load controllers | Raspberry Pi 4 (demo); ESP32 would suffice in production | ~$5 in quantity |

The ESP32 — a microcontroller with integrated Wi-Fi costing under $5 — is representative of what's already inside most network-connected appliances today. **Manufacturers have no technical or cost barrier to incorporating OpenADR 3.**

## Software

The gateway runs [Home Assistant](https://www.home-assistant.io/) — free, open-source home automation software used in approximately 2 million homes worldwide — augmented with our [OpenADR 3 client libraries](/software).

- **Automatic discovery**: The gateway advertises itself on the LAN via mDNS; appliances discover and connect without configuration
- **Open-source**: All code is published in our [GitHub repositories](https://github.com/grid-coordination)
- **Standards-based**: OpenADR 3 end-to-end, no proprietary protocols

## The Prices

The demo used "SpringHDP" prices from CalFlexHub, derived from real CAISO wholesale prices with the vertical scale stretched for visibility. Time was compressed so each hour played out in 5 seconds, making a full "day" visible in two minutes. OpenADR 3 handles arbitrary price intervals — most dynamic pricing programs worldwide use hourly granularity today.

## Why This Matters

This demo was built by **four volunteers in their spare time over one month**, using freely available open-source software. If four people can build a complete grid-to-appliance dynamic pricing system in a month, manufacturers will have no difficulty incorporating OpenADR 3 into their products.

The system illustrates that flexible demand appliance standards mandating network connectivity and open protocols are **easily implemented at low or no incremental cost**. The technology is ready. The regulatory framework is catching up. The only thing missing is the mandate.

## Key Takeaways

- **OpenADR 3 is ready today** — not a future promise
- **Inexpensive hardware** — runs on a $5 microcontroller
- **Open-source software** — no vendor lock-in
- **Automatic configuration** — mDNS discovery, zero manual setup
- **Standards-based** — one open protocol from grid to appliance
- **Local control** — works without the cloud once prices are received

## Learn More

- [Our software libraries](/software) — OpenADR 3 implementations in Clojure and Python
- [OpenADR Alliance](https://www.openadr.org/) — the standard behind grid-to-customer coordination
- [2025 CA Demand Flexibility Summit](https://www.energy.ca.gov/event/meeting/2025-05/2025-california-demand-flexibility-summit) — the CEC event where this was demonstrated
- [Demo handout (PDF)](/presentations/openadr3-demo-handout.pdf) — the one-page flyer from the event
