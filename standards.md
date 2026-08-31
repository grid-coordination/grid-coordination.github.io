---
layout: default
title: Related Standards
permalink: /standards
---

# Related Standards

A grid signal has to travel a long way to reach the appliance that acts on it: from the utility, across the Internet, into the house, and then between the devices inside it. No single standard covers that whole path, and none should.

Three open standards cover it between them, and Grid Coordination backs all three.

## OpenADR 3

**The grid to the customer, over the Internet.**

[OpenADR 3](https://www.openadr.org/) carries dynamic prices, demand response events, grid alerts and power limits from a utility to whatever the customer chooses to receive them: an appliance directly, a hub they own, or a service provider they picked. The server address is a setting the customer controls, so no aggregator sits in the path unless the customer wants one there.

It is the only one of these standards designed for the utility-to-customer leg, and it runs on ordinary web technology (HTTPS, JSON, OAuth2, MQTT for push) on hardware costing a few dollars.

Grid Coordination is an active participant in the OpenADR Alliance. We proposed and led the working group that added the [push notification protocol](https://github.com/grid-coordination/openadr3-specification/blob/main/doc/OpenADR3%20Object%20Operation%20Notifications%20via%20Additional%20Protocols.md) adopted in OpenADR 3.1, publish [open-source libraries](/software) in Clojure and Python, and operate a [free public price server](https://github.com/grid-coordination/price-server-user-guide) carrying real California prices.

## Matter

**The home network to the devices in it.**

[Matter](https://csa-iot.org/all-solutions/matter/) is the open smart home standard from the Connectivity Standards Alliance, shipping today in ordinary consumer products and supported by every major ecosystem. Its energy management clusters (Device Energy Management, Energy EVSE, Water Heater Management, Electrical Power and Energy Measurement) let a home energy manager see what devices are doing and shift what they plan to do.

Matter runs over the home network and does not reach the utility, which is exactly right: paired with OpenADR 3 it completes the path, with prices and limits arriving from the grid over the Internet and reaching every device over Wi-Fi, Ethernet or Thread.

## eBus

**The home's energy infrastructure, coordinating with itself.**

[eBus, the Electrification Bus](https://ebus.energy), is an open framework for the devices that make up a home's electrical system: the panel, the meter, inverters, batteries, EV charging equipment and the microgrid interconnect device. These are not consumer smart home products, and they have a coordination problem Matter was never meant to solve. Today each one meters what it can and shares nothing, control paths run through vendor clouds that fail during the outages when local coordination matters most, and every device-to-device integration is a bespoke project.

eBus defines how these devices discover each other, publish what they measure, and coordinate locally without the cloud in the loop.

Grid Coordination developed the eBus framework. The [specification](https://github.com/electrification-bus/specification) and reference work are public.

## The three together

| Standard | Covers | Transport |
|---|---|---|
| **OpenADR 3** | Utility to the customer's own equipment | The Internet |
| **Matter** | Home energy manager to consumer devices | The home network |
| **eBus** | Home energy infrastructure devices to each other | The home network |

Each is open, each is implementable on inexpensive hardware, and none of them requires an aggregator or a manufacturer's cloud.

## Other standards

Several other standards address parts of this problem. Some are complementary, some fall short in ways worth understanding before they are written into regulation.

**[Read the assessment](/standards/other)** &mdash; S2, AHRI 1380, CTA-2045 (EcoPort), IEEE 2030.5 and OCPP.
