---
layout: default
title: Resources
permalink: /resources
---

# Resources

Projects, articles, and references aligned with the Grid Coordination architecture — open protocols, direct utility-to-home communication, and site-level coordination rather than per-device cloud control.

## Open Infrastructure

### Public OpenADR 3 Price Server

A live, public electricity price service built on [clj-oa3-vtn](https://github.com/grid-coordination/clj-oa3-vtn), serving hourly marginal prices from the CAISO Day-Ahead Market via [GridX](https://www.gridx.com/) for PG&E and SCE rate schedules.

| Resource | Link |
|----------|------|
| REST API base (OpenADR 3.1.0) | `https://price.grid-coordination.energy/openadr3/3.1.0/` |
| Try it in a browser | [`/programs?limit=5`](https://price.grid-coordination.energy/openadr3/3.1.0/programs?limit=5) |
| MQTT push notifications | `mqtt.grid-coordination.energy` (ports 1883 / 8883) |
| User guide & tutorials | [price-server-user-guide](https://github.com/grid-coordination/price-server-user-guide) |
| VTN server source | [clj-oa3-vtn](https://github.com/grid-coordination/clj-oa3-vtn) |

No authentication required. About 1,700 programs: PG&E and SCE tariffs across 105 distribution circuits and substations, prices computed from published PG&E, SCE, SDG&E, LADWP and City of Palo Alto rate schedules, and hourly marginal GHG emissions for 11 California grid regions. Tutorials for Python, Clojure, and Rust clients.

## Real-World Deployments

### PG&E + Itron AMI 2.0 + SPAN Edge &mdash; Pilots for Transformer-Aware Load Coordination

[Canary Media &mdash; "As Californians electrify, can this tech combo prevent grid overload?"](https://www.canarymedia.com/articles/utilities/as-californians-electrify-tech-prevent-grid-overload) (March 2026)

Pacific Gas & Electric, California's largest utility, is piloting a two-device architecture that pushes grid coordination all the way to the service-transformer level:

- **Itron AMI 2.0 smart meters** &mdash; app-capable meters that communicate not only with the utility but with *each other* over their shared wireless mesh. Neighboring meters on the same service transformer can now sum local demand, compute how much headroom the transformer has, and feed that data back to connected devices in customers' homes.
- **SPAN Edge** &mdash; a smart-panel device that plugs directly into the utility meter and throttles household circuits (EV chargers, HVAC, dryers) when the transformer is approaching its limit.

Together they let customers electrify without triggering panel or transformer upgrades that can cost anywhere from a few thousand to fifty thousand dollars, and let PG&E defer billions in grid investment. The pilot begins with PG&E employees' homes, expanding to volunteer customers in 2027; ~1,000 homes will get Itron's AMI 2.0 upgrade this year, potentially scaling to hundreds of thousands through 2030.

This is exactly the architecture Grid Coordination advocates: **dynamic power limits at the site level**, communicated over open networks to devices that respond autonomously &mdash; not per-device control from manufacturer clouds.

*Grid Coordination's founder participates in this pilot through one of the partner organizations.*

## Past demonstrations

Grid Coordination has demonstrated live OpenADR 3 dynamic pricing at the [2026 CEC/EPRI Electrification Summit](https://www.energy.ca.gov/event/workshop/2026-06/2026-cecepri-electrification-summit), the [CalFlexHub Symposium 2026](https://calflexhub.lbl.gov/events/) at Lawrence Berkeley National Lab, and the [2025 California Demand Flexibility Summit](https://www.energy.ca.gov/event/meeting/2025-05/2025-california-demand-flexibility-summit) hosted by the California Energy Commission. See [the demo](/demo) for what the system does and how it is built.
