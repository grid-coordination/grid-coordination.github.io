---
layout: default
title: Related Standards
permalink: /standards
---

# Related Standards

Grid Coordination builds on and advocates for open standards that enable interoperability across the electric grid. Here are the key standards in this space.

## OpenADR 3

[OpenADR 3](https://www.openadr.org/) is the open standard for communicating demand response signals, dynamic pricing, and grid events from utilities to customers. It defines the protocol layer between utility price servers (VTNs) and customer energy management systems (VENs).

Grid Coordination is an active participant in the OpenADR Alliance. We contributed the push notification protocol extension adopted in OpenADR 3.1 and publish [open-source libraries](/software) implementing the standard in Clojure and Python. Our [live price server](https://github.com/grid-coordination/price-server-user-guide) is a public OpenADR 3.1.0 deployment.

## S2 Standard

[S2](https://s2standard.org/) is a communication standard for energy flexibility in homes and buildings, developed in the Netherlands and gaining international traction. While OpenADR 3 defines the protocol between the grid and the customer, S2 defines the protocol between a Customer Energy Manager (CEM) and the smart appliances within a building.

S2 uses a model of **energy flexibility patterns** rather than device-specific commands. A Resource Manager (RM) in each appliance communicates what the device *can* do flexibly, while the CEM decides *how* to use that flexibility based on price signals, grid constraints, and user preferences. This separation keeps appliance manufacturers in control of their devices while enabling coordinated optimization.

S2 is complementary to OpenADR 3: OpenADR 3 carries price and constraint signals from the grid to the home, while S2 enables the home energy management system to coordinate flexible loads in response.

- [S2 Standard website](https://s2standard.org/)
- [S2 Whitepaper (PDF)](https://s2standard.org/wpcms/wp-content/uploads/2023/09/S2-Whitepaper-202309-1.pdf)
- [S2 on GitHub](https://github.com/flexiblepower)

## AHRI 1380

AHRI 1380 is a standard from the Air-Conditioning, Heating, and Refrigeration Institute defining a communication interface for demand-responsive residential HVAC equipment. It specifies how HVAC systems should receive and respond to external signals — including price signals and load-shed requests — enabling them to participate in demand flexibility programs.

Grid Coordination participates in the AHRI 1380 working group to ensure alignment with the broader grid coordination architecture.
