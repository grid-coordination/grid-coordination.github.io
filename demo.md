---
layout: default
title: Live Demos
permalink: /demo
---

# Price-based Demand Flexibility with OpenADR 3

**A complete grid-to-appliance dynamic pricing system &mdash; running on low-cost single-board computers, built entirely from open standards and open-source software.**

Hourly OpenADR 3 prices stream from the cloud to a customer gateway, then flow over the local network to appliances &mdash; an EV charger, water heater, and HVAC system &mdash; that each autonomously optimize against the current price. No proprietary clouds. No per-device control. No aggregators. Just dynamic prices, open protocols, and software running on inexpensive microcontrollers.

**This is not a simulation.** It's a working system, built by four volunteers in one month, that you can build yourself.

![The demonstration board: a house outline with an OpenADR 3 price server in the cloud, a Home Assistant gateway inside the home, and tablets showing an EV charger, water heater and HVAC unit each responding to the current hourly price](/images/photos/openadr3-demo-board.jpg)

<p class="caption">The board as demonstrated at the 2026 CEC/EPRI Electrification Summit. Every screen is live: the gateway is fetching real California prices, and each appliance is deciding what to do with them on its own.</p>

## What We Built

A grid price server communicates hourly dynamic prices via [OpenADR 3](https://www.openadr.org/) to a customer gateway, which then distributes those prices over the local network to mock appliances — an EV charger, water heater, and HVAC system. Each appliance independently optimizes its behavior based on the current and forecast price.

### The Architecture

![Grid price server in the cloud sends OpenADR 3 over the Internet to a Home Assistant gateway in the home, which republishes prices on the local network to an EV charger, water heater and HVAC unit](/images/diagrams/demo-architecture.svg)

- The **gateway** receives prices from the cloud and re-publishes them locally
- Each **appliance** discovers the gateway automatically via mDNS and connects
- Appliances respond to price signals autonomously — no aggregator, no proprietary cloud

### How Appliances Use Prices

Each load optimizes against the current price and forecast. The demo uses a simple algorithm for illustration — real products would be more sophisticated, optimizing across many hours using thermal storage (water heater), electrical storage (battery), or deferred service delivery (pool pump, EV charging).

When the price is low, deferrable loads run. When the price spikes, they curtail. The gateway computes an effective **local price** that accounts for self-generation and storage, so appliances always see the most relevant signal.

## Hardware

| Component | Hardware | Cost |
|-----------|----------|------|
| Gateway | Raspberry Pi 4 | ~$35 |
| Load controllers | Raspberry Pi 4 (demo); ESP32 would suffice in production | ~$35 as demonstrated; ~$5 in quantity for an ESP32 |

The ESP32 — a microcontroller with integrated Wi-Fi costing under $5 — is representative of what's already inside most network-connected appliances today. **Manufacturers have no technical or cost barrier to incorporating OpenADR 3.**

## Software

The gateway runs [Home Assistant](https://www.home-assistant.io/) — free, open-source home automation software used in approximately 2 million homes worldwide — augmented with our [OpenADR 3 client libraries](/software).

- **Automatic discovery**: The gateway advertises itself on the LAN via mDNS; appliances discover and connect without configuration
- **Standards-based**: OpenADR 3 end-to-end, no proprietary protocols

## The Prices

The demo uses live California electricity prices streamed from our own public [Grid Coordination price server](https://github.com/grid-coordination/price-server-user-guide) &mdash; the same OpenADR 3.1.0 service anyone can connect to today. For presentation, time is compressed so each hour plays out in 5 seconds, making a full "day" visible in about two minutes. OpenADR 3 handles arbitrary price intervals &mdash; most dynamic pricing programs worldwide use hourly granularity today.

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

## Where We've Demonstrated

We've shown this complete grid-to-appliance Price-based Demand Flexibility with OpenADR 3 system at:

- **June 10, 2026** &mdash; [2026 CEC/EPRI Electrification Summit](https://www.energy.ca.gov/event/workshop/2026-06/2026-cecepri-electrification-summit) ([agenda](https://www.energy.ca.gov/media/12794))
- **April 15, 2026** &mdash; [CalFlexHub Symposium 2026](https://calflexhub.lbl.gov/events/) at Lawrence Berkeley National Lab
- **May 2025** &mdash; [2025 California Demand Flexibility Summit](https://www.energy.ca.gov/event/meeting/2025-05/2025-california-demand-flexibility-summit), hosted by the California Energy Commission

## Learn More

- [Our software libraries](/software) — OpenADR 3 implementations in Clojure and Python
- [OpenADR Alliance](https://www.openadr.org/) — the standard behind grid-to-customer coordination
- [Live price server](https://github.com/grid-coordination/price-server-user-guide) — public OpenADR 3 price server serving live California electricity prices, with user guide and client tutorials
- [Demo handout (PDF)](/presentations/openadr3-demo-handout.pdf) — the one-page flyer from the event
