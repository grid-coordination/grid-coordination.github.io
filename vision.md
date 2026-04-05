---
layout: default
title: Vision
permalink: /vision
---

# Vision: The Future of Grid Coordination

Effective grid coordination requires solving two distinct but complementary problems. Understanding this distinction is essential to designing the right architecture.

## The Historical Constraint

For most of its history, the grid had no way to coordinate with customer loads in real time. Infrastructure was therefore sized for **worst-case demand** &mdash; the peak that might occur only a few hours a year. Customer consumption was treated as an exogenous input: whatever loads customers chose to run, the grid had to accommodate.

That constraint no longer holds. **IP networking**, **open grid-coordination protocols**, and **low-cost networked microcontrollers and single-board computers** now make it practical to communicate dynamic prices and power limits to every flexible load in every home &mdash; and for those loads to respond autonomously.

This changes what the grid has to do. It no longer needs to be sized for the worst case; it can be *coordinated* for the actual case. The two problems below &mdash; macro balancing and micro distribution protection &mdash; are both now tractable through communication rather than oversizing.

## Problem 1: Macro Grid Coordination

The overall electric grid must continuously balance generation with consumption. Today, this is managed through a combination of static time-of-use rates, grid emergency alerts, and aggregator-mediated demand response.

The aggregator model worked when a home had a single controllable load. But as electrification accelerates, a typical home may have an EV charger enrolled with one aggregator, HVAC controlled by another, and a water heater managed by a third. These aggregators operate independently, with no visibility into each other's actions or the customer's overall energy situation.

**Site-level optimization is impossible when control is fragmented across multiple aggregators, each managing a single device in isolation.**

The solution is **dynamic pricing** &mdash; hourly or sub-hourly price signals that encode the real-time state of grid supply and demand into a universally understood value. Every customer's energy management system can independently optimize across *all* loads and distributed energy resources based on price, local generation, storage state, and customer preferences.

No per-device enrollment. No proprietary protocols. No fragmentation. Just a price signal and a capable local EMS.

## Problem 2: Micro Grid Coordination

Price alone cannot solve the local problem of managing physical constraints on the distribution network. Even if every customer responds optimally to price signals, the distribution transformer serving a specific neighborhood has a finite capacity. When everyone arrives home and plugs in their EV, the transformer may overload regardless of price.

This requires **power limits** &mdash; explicit, per-customer caps on import (and export) power that protect distribution infrastructure.

## Why Both Are Necessary

| Mechanism | Solves | Granularity | Scope |
|-----------|--------|-------------|-------|
| **Dynamic pricing** | Grid-wide supply/demand balance | Economic &mdash; shifts energy in time | Macro: all customers |
| **Power limits** | Distribution network protection | Physical &mdash; caps instantaneous power | Micro: per-transformer |

**Price is necessary but not sufficient.** Without power limits, price-responsive customers on an overloaded transformer could still cause physical damage.

**Power limits are necessary but not sufficient.** Without price signals, customers have no economic motivation to shift energy usage, and the grid cannot leverage the flexibility of millions of distributed loads and resources.

Together, these two signals give a local energy management system everything it needs to optimize autonomously:

- Minimize energy cost based on current and forecast prices
- Respect the import power limit at all times
- Prioritize loads based on customer preferences
- Dispatch local resources (solar, battery) to reduce cost and stay within limits

## From Per-Device Control to Site-Level Optimization

The industry is evolving along a clear trajectory:

| | Per-Device Aggregator DR | Explicit Site-Level DR | Implicit DR via Price |
|---|---|---|---|
| **Mechanism** | Aggregator controls individual appliances via OEM cloud | Utility sends site-level commands | Utility publishes price; EMS decides |
| **Customer agency** | Minimal | Limited | Full |
| **Multi-device coordination** | Poor | Good | Good |
| **Scalability** | Poor | Moderate | Excellent |

Per-device aggregator control was viable when a home had one or two controllable loads. It cannot scale to the electrified home with EV charger, heat pump HVAC, heat pump water heater, battery storage, and solar PV &mdash; all of which need holistic coordination at the site level.

**Implicit demand response via dynamic pricing is the scalable, customer-friendly endpoint of this evolution.** The energy management system receives price signals and power limits, and optimizes across all loads and resources based on customer preferences. This is the architecture Grid Coordination advocates for, builds toward, and works to embed in standards and policy.

## This Is Being Built

The architecture described above is no longer speculative. Pacific Gas & Electric is [piloting transformer-aware smart meters and meter-mounted smart panels](https://www.canarymedia.com/articles/utilities/as-californians-electrify-tech-prevent-grid-overload) that communicate directly with home energy devices &mdash; enforcing site-level power limits without per-device aggregator control. See [Resources](/resources) for more deployments and references.
