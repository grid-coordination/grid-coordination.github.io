---
layout: default
title: "Other Standards"
permalink: /standards/other
---

# Other Standards

Beyond the three we back, several standards address parts of grid coordination. This is an honest assessment of each: what it does, and where it stops. Our test throughout is simple. **Does the open interface reach the appliance itself, can the customer choose which server it talks to, and does it carry a price and a limit?**

See [Related Standards](/standards) for OpenADR 3, Matter and the Electrification Bus.

## S2

**Complementary, and worth watching.**

[S2](https://s2standard.org/) is a European standard for energy flexibility in homes and buildings. Where OpenADR 3 carries signals from the grid to the customer, S2 defines how a Customer Energy Manager talks to the flexible appliances inside a building.

Its central idea is good: S2 exchanges **flexibility patterns** rather than device-specific commands. A Resource Manager in each appliance describes what the device *can* do, and the energy manager decides how to use that flexibility given prices, constraints and the customer's preferences. That keeps the manufacturer in control of the appliance and the customer in control of the outcome, which is the right division.

S2 and OpenADR 3 are complementary rather than competing, and S2 occupies roughly the same layer as Matter's energy clusters.

- [S2 Standard website](https://s2standard.org/)
- [S2 whitepaper (PDF)](https://s2standard.org/wpcms/wp-content/uploads/2023/09/S2-Whitepaper-202309-1.pdf)
- [S2 on GitHub](https://github.com/flexiblepower)

## AHRI 1380

**Certifies the cloud, not the appliance.**

AHRI 1380 is the Air-Conditioning, Heating, and Refrigeration Institute's standard for demand-responsive residential HVAC. In principle it defines how HVAC equipment receives and responds to external signals.

In the implementations we have examined, manufacturers satisfy it by connecting the equipment to their own cloud over a private protocol, then exposing a grid interface from that cloud. The appliance in the home still speaks nothing open, the customer cannot point it anywhere else, and the capability disappears if the manufacturer stops running the service.

Grid Coordination participates in the AHRI 1380 working group and argues for a revision that puts an open interface on the equipment itself.

## CTA-2045, marketed as EcoPort

**The open interface stops at the socket.**

CTA-2045 standardizes a physical communications port on an appliance, most commonly an electric storage water heater. Washington, Oregon, Colorado and New York now require it on new units.

The socket is standardized. Nothing above it is. Each vendor's plug-in module speaks its own language upstream, so two compliant water heaters need not interoperate and neither is reachable by anyone but its module's vendor. The module a customer has to buy and install runs well over $150, which has proven an insurmountable deployment obstacle in practice.

The assumptions behind CTA-2045, that appliances lack microcontrollers and that network interfaces are too expensive to integrate, are no longer true. **It should be retired, not written into new rules.**

## IEEE 2030.5

**Strong at commanding one inverter, which is the wrong unit.**

[IEEE 2030.5](https://standards.ieee.org/ieee/2030.5/5897/) is genuinely capable for distributed energy resource control and is mandated in California for inverter communications under Rule 21.

Its limitation is the unit of management. A modern home has solar, a battery and one or two bidirectional car chargers. Control each inverter separately and nobody is managing the total. What belongs at the grid boundary is one import and export limit for the whole service connection, with the house allocating within it.

In residential practice manufacturers translate or proxy 2030.5 through their own systems, no seller of electricity offers customers a direct connection, and customers cannot repoint their equipment at a server of their choosing.

## OCPP

**Built for a different job.**

[OCPP](https://openchargealliance.org/) was designed for commercial and public EV charging, and it does that well. Almost no US residential chargers implement it, and where it is supported the connection is not offered to the customer: it points at the vendor's cloud.

There is no need for a protocol unique to EV chargers. A car charger needs the same two facts every other flexible load needs: what power costs now and next, and how much this connection may draw.

## The pattern

Four of these five stop short of the appliance, aim at the wrong unit, or route through a cloud the customer has no relationship with. That is not a failure of intent; each was a serious effort. But it is the reason we argue for **one open protocol from the grid to the house, and one open protocol inside it**, rather than a new protocol for every appliance category and a rulemaking behind each.
