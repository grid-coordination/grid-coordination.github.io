---
layout: default
title: Resources
permalink: /resources
---

# Resources

Projects, articles, and references aligned with the Grid Coordination architecture — open protocols, direct utility-to-home communication, and site-level coordination rather than per-device cloud control.

## Real-World Deployments

### PG&E + Itron AMI 2.0 + SPAN Edge &mdash; Pilots for Transformer-Aware Load Coordination

[Canary Media &mdash; "As Californians electrify, can this tech combo prevent grid overload?"](https://www.canarymedia.com/articles/utilities/as-californians-electrify-tech-prevent-grid-overload) (March 2026)

Pacific Gas & Electric, California's largest utility, is piloting a two-device architecture that pushes grid coordination all the way to the service-transformer level:

- **Itron AMI 2.0 smart meters** &mdash; app-capable meters that communicate not only with the utility but with *each other* over their shared wireless mesh. Neighboring meters on the same service transformer can now sum local demand, compute how much headroom the transformer has, and feed that data back to connected devices in customers' homes.
- **SPAN Edge** &mdash; a smart-panel device that plugs directly into the utility meter and throttles household circuits (EV chargers, HVAC, dryers) when the transformer is approaching its limit.

Together they let customers electrify without triggering panel or transformer upgrades that can cost anywhere from a few thousand to fifty thousand dollars, and let PG&E defer billions in grid investment. The pilot begins with PG&E employees' homes, expanding to volunteer customers in 2027; ~1,000 homes will get Itron's AMI 2.0 upgrade this year, potentially scaling to hundreds of thousands through 2030.

This is exactly the architecture Grid Coordination advocates: **dynamic power limits at the site level**, communicated over open networks to devices that respond autonomously &mdash; not per-device control from manufacturer clouds.

*Grid Coordination's founder participates in this pilot through one of the partner organizations.*
