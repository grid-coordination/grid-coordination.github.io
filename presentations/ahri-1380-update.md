---
marp: true
theme: default
paginate: true
header: "Grid Coordination"
footer: "DC Jackson"
style: |
  section {
    font-size: 24px;
  }
  h1 {
    color: #2a6e3f;
    font-size: 36px;
  }
  h2 {
    color: #333;
    font-size: 30px;
  }
  table {
    font-size: 20px;
  }
  blockquote {
    border-left: 4px solid #2a6e3f;
    padding-left: 1em;
    color: #555;
    font-style: italic;
  }
  .columns {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }
---

# AHRI 1380
# Updating to "-2026" from "-2019"

Don Jackson

---

# Proposed Goals for AHRI 1380-2026

Define a standard that enables HVAC systems to participate in demand flexibility, in order to:

- Provide customers the comfort they desire, at the **lowest energy cost**
- Coordinate with the electric grid to **reduce peak load events**, lowering infrastructure costs
- **Shift energy usage** to minimize both environmental impact (GHG) and cost

### Enable demand flexibility control by any or all of:

- Customer
- Utility
- Aggregator (including the HVAC manufacturer acting as aggregator)

---

# AHRI 1380-2019 Protocols

### OpenADR 2.0b
- HVAC system connects via Wi-Fi and/or Ethernet
- VEN (client) typically resides in **manufacturer's cloud**
- Connection between HVAC system and cloud uses proprietary protocol

> Are there ANY native-VEN HVAC systems?

### CTA-2045-A
- A port enabling an aftermarket UCM to control the HVAC system
- UCM's connection to DRP uses unspecified protocol

> Are there ANY HVAC systems that support CTA-2045?

---

# Educated Guesses & Assumptions

Virtually all AHRI 1380-2019 compliant HVAC systems do so via:

- OpenADR 2.0b VEN residing in the **manufacturer's cloud**
- Wi-Fi interface on HVAC system
- **No** HVAC systems support OpenADR native VENs
- **No** HVAC systems support CTA-2045 ports

---

# Industry Trends

- **Dynamic pricing** is superior to traditional DR events — CPUC & CEC transitioning
- Flexible-demand appliances per household are **growing** — need coordinated management
- Grid coordination transitioning from **device** to **site**
  - Dynamic power import/export limits per site (NEC-705.13 & UL-3141)
  - Site management will occur **locally**, not in the cloud
- **OpenADR 3.1** supports everything 2.0b does, plus:
  - Both cloud-to-cloud AND cloud-to-device communication
  - Simpler & easier to develop and deploy
- **Matter** adopted for smart-appliance interoperability (800+ companies)
  - Does not provide grid-to-customer coordination alone
  - Combined with OpenADR 3.1: local HEMS controls via Matter

---

# Functional Control and Demand Response

- Device behavior is altered via **functional-control commands**
- Optimal translation requires **local customer context**
- The translation location must be **customer's choice**: device, local HEMS, or ASP
- Translation **must not** be locked in the manufacturer's cloud

> Local HEMS is the best location to translate price & DR events to functional-control commands

---

# Ensured vs. Enabled

<div class="columns">
<div>

### Ensured
The HVAC system supports:
- An open/standard protocol for flexible demand control
- Server URL is customer-configurable
- Network interface(s) for LAN/Internet

**Fully capable of participating in demand flexibility with no additional cost or effort**

</div>
<div>

### Enabled
The HVAC system supports:
- A connector/port for another device
- That device provides flexible demand control by unspecified means

**Requires additional cost and effort to participate**

</div>
</div>

---

# Assessing AHRI 1380-2019

| Compliance Type | Mechanism |
|----------------|-----------|
| **Ensured** | Wi-Fi + OpenADR 2.0b VEN in manufacturer cloud |
| **Enabled** | CTA-2045-A |

> Experience with CTA-2045 for water heaters has clearly demonstrated that the cost and installation of a UCM is too large, resulting in very poor connection rates. CTA-2045 is obsolete and should be EOL'd.

---

# Implications from Trends

- **Begin transition** from OpenADR 2 to OpenADR 3.1
- **Define native HVAC system control** to enable:
  - Coordinated management of all home appliances
  - Allocation of site capacity limits to specific appliances
- **Add Matter support** to native HVAC systems for:
  - Functional control by Matter-based HEMS
  - Customer integration into "whole home" management apps
- **Drop CTA-2045 support**:
  - Few/no HVAC systems support it
  - Has failed for water heater DR with plenty of time to succeed

---

# AHRI 1380-2026 Proposal: Networking

### HVAC systems must support (or be capable of supporting):
- **Wi-Fi**
- **Cellular modem**
- **Ethernet**

### Implementation:
- HVAC system may directly integrate any or all interfaces
- HVAC system **must** provide a **USB-C port** for network interface dongles
- Customer (or DRP) adds non-integrated interfaces as needed

---

# AHRI 1380-2026 Proposal: Protocols

Two distinct compliance types — a system **must** support one, **may** support both:

### Native
Protocol(s) provided directly & locally by the HVAC system:
- **OpenADR 3.1 VEN** — Mandatory (MUST), VTN URL customer-configurable
- **Matter 1.4+** — Optional (SHOULD): DEM, DEM Mode, Thermostat clusters

### Cloud
Protocol(s) provided via the manufacturer's cloud:
- **OpenADR** — Mandatory (MUST)
  - 3.1 VEN: Preferred (SHOULD)
  - 2.0b VEN: Allowed (MAY) during transition
- **Home Connectivity Alliance** — Optional (MAY)

---

# Compliance/Certification Options

| Option | Protocol | Networking |
|--------|----------|------------|
| **2026-Cloud + 2019-Networking** | OA 2.0b or 3.1 in cloud | Wi-Fi and/or Ethernet |
| **2026-Cloud + 2026-Networking** | OA 2.0b or 3.1 in cloud + optional HCA | Integrated + USB-C |
| **2026-Native + 2026-Networking** | OA 3.1 integrated + optional Matter | Integrated + USB-C |

A compliant HVAC system must specify which option(s) it supports.

Enables existing products to comply while providing a clear transition path.

---

# Where the Puck Is Going: Grid Coordination

- "Macro" coordination will transition from DR events to **highly dynamic pricing**
- "Micro" coordination will support **dynamic capacity management** per site
  - "Current price is P $/kWh, your maximum site import is N Amps"
- HEMS will **autonomously** control loads based on price, capacity limits, customer preference, local generation, and storage

> Native control of HVAC power & energy is the only way to support these use cases.
> HVAC manufacturers should focus on and prioritize native protocol support.
> OpenADR 3.1 supports BOTH cloud-to-cloud AND cloud-to-native use cases.

---

# Where the Puck Is Going: HVAC Systems

| From | To |
|------|----|
| Natural gas | Electricity (heat pump) |
| Fixed speed | Variable speed (inverters) |
| One zone | Multiple zones (or mini-splits) |
| DR client in manufacturer cloud | DR client in HVAC system |
| Proprietary control protocol | Open & standard protocol |
| Controller in thermostat | Controller in air handler |
| Thermostat UI | Tablet & phone apps |
| Central thermostat sensor | Distributed IoT sensors |

---

# CEC and Demand Flexibility

The CEC has begun a series of dockets to define **Flexible Demand Appliance Standards** (FDAS):

- **Docket 24-FDAS-03** for Low-Voltage Thermostats (September 2024)
- **Docket 24-FDAS-04** for Electric Vehicle Supply Equipment (October 2024)

> It behooves AHRI 1380 to support potential regulatory mandates and future rebate/incentive requirements.

The 1380-2026 proposals provide a **smooth transition path** from today to tomorrow, enabling HVAC systems to "skate to where the puck is going."

---

# Exit Protocols & MITO

### Exit Protocol ("Snapback")
- Simultaneous startup of many HVAC systems after DR event stresses the grid
- Solutions: randomized duration offsets, staggered cancellation events
- Likely a server implementation issue, not a protocol issue

### Maximum Indoor Temperature Offset (MITO)
Most useful HVAC controls for DR:
- **Mode**: Heat pump only, vacation, off
- **Setpoint**: Raise (cooling) or lower (heating) to attenuate power
- **Power adjustment**: Variable-speed systems support throttle control
- **Zone**: Mode and setpoint per zone

> Variable power adjustment via Matter DEM and DEM-mode clusters provides the most granular control. Local control is crucial for HEMS.
