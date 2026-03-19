---
marp: true
theme: default
paginate: false
style: |
  section {
    font-size: 20px;
    padding: 2rem;
  }
  h1 {
    color: #2a6e3f;
    font-size: 32px;
    text-align: center;
    margin-bottom: 0.5rem;
  }
  h2 {
    color: #333;
    font-size: 22px;
    margin-top: 0.5rem;
  }
  .columns {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }
---

# Price-based Demand Flexibility with OpenADR 3
## Inexpensive, Simple, and Ready

**Don Jackson, Bruce Nordman, Lazlo Paul, Alvin Tan**

<div class="columns">
<div>

## What This Demonstrates

A grid price server uses **OpenADR 3** to communicate hourly dynamic prices to a customer's gateway device that then controls example loads. Both the gateway and load controllers are implemented using low-cost single-board computers and open-source OpenADR 3 code libraries.

This system illustrates that flexible demand appliance standards mandating network connectivity and open/standard protocols are **easily implemented at low/no cost** by appliance manufacturers today.

## Hardware

- **Gateway:** Raspberry Pi 4 (~$35) — reasonable for production
- **Load controllers:** Raspberry Pi 4 for demo; a microcontroller would easily suffice (ESP32 with Wi-Fi, ~$5 in quantity)
- Four volunteers built this demo in their spare time using open-source software over one month

## Retail Prices

The prices are "SpringHDP" from CalFlexHub, derived from real CAISO prices with the vertical scale stretched for visibility. Time is compressed: each hour = 5 seconds, so each "day" takes 2 minutes.

</div>
<div>

## Gateway Software

The gateway includes **Home Assistant** augmented with software to connect and receive prices from a cloud-based price server, distributing prices over the LAN using OpenADR 3.

Home Assistant is free and open-source, used in ~2 million homes worldwide with 3,000+ integrations (Matter, Z-Wave, Zigbee, SmartThings, and more).

## Automatic Configuration

The gateway advertises itself on the LAN; appliances discover and connect automatically via **multicast DNS (mDNS)** — the same technology used to locate printers.

## Why a Gateway?

Only one device needs to know the retailer and tariff. It can also:
- Determine the correct **local price**
- Host algorithms for optimizing legacy loads
- Alert the customer if connection is lost
- Receive energy reporting data from devices

## Grid-to-Customer Communication

OpenADR 3 supports: highly dynamic prices + GHG data, direct controls for aggregators, dynamic operating envelopes for distribution capacity, and significant grid events.

</div>
</div>
