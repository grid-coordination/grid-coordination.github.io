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

# Grid Coordination
# For Residential Customers

DC Jackson

---

# Two Grid Coordination Problems

<div class="columns">
<div>

### "Macro" Grid Coordination
**Managing the Grid**
- Highly dynamic prices
- Demand-response events
- Functional control of devices
- Grid events (FlexAlerts)

</div>
<div>

### "Micro" Grid Coordination
**Managing the Distribution Network**
- Functional control at the device level (EVSE, DER inverter)
- Dynamic control of customer-site service level (import & export)
- Can't do much of this today: static sizing based on predicted worst-case load

</div>
</div>

---

# Trends: Grid

- Increasing agreement that **highly dynamic pricing** is superior to traditional DR events
- CPUC & CEC vision: transition to highly dynamic pricing, with LSE/IOU pilots underway
- The number of flexible-demand appliances per household is **growing**
  - Multiple appliances need to be managed "in concert"
  - Unlikely that all appliances share the same manufacturer
- Grid coordination is transitioning from the **device** to the **site**
  - Set a dynamic power import/export limit on the site, not per device
  - The site manages loads & appliances via PCS & HEMS (NEC-705.13 & UL-3141)
- Site power & energy management will most likely occur **locally, not in the cloud**

---

# Trends: Smarter Infrastructure

### Smart Meters
- Improved sensors with high sample-rate ADCs
- Network connectivity to the home LAN and Internet
- Third-party meter apps and platform standards (GEISA)

### Smart Electric Panels
- Revenue-grade metering on I/O lugs & every circuit
- Relays on each circuit
- Network connectivity: Ethernet and Wi-Fi
- Integrated Power Control Systems (NEC-705.13 & UL-3141)
- Integrated Home Energy Management System (HEMS)
- Gateway processor running Linux

---

# Trends: Matter

- Widespread agreement & adoption of **Matter** as the open standard for smart-appliance & IoT interoperability
  - Apple, Google, Amazon, LG, 800+ others
- However, Matter **does not** provide grid-to-customer coordination
- Matter alone cannot provide a complete grid-to-customer flexible demand solution

### The Combination

- **HEMS + OpenADR 3.1** can shift appliance energy usage via Matter
- **PCS** can attenuate appliance power via Matter
  - Better customer experience than power-cycling via relays
  - Relays provide a fail-safe backstop

---

# Grid Coordination with Matter

**Use OpenADR 3.1** to obtain DR events and electricity prices from the cloud/Internet to the home

**Use Matter** within the home to control the power and shift energy of appliances

### Two Protocol Layers

| Layer | Protocol | Scope |
|-------|----------|-------|
| Grid-to-home | OpenADR 3.1 | Prices, DR events, power limits |
| Within-home | Matter | Device control, energy management |

---

# The Future Residential Utility Customer

### Smart Meter capabilities:
- Power import & export measurement
- Grid health monitoring via high sample-rate measurements
- Communication with LSE via private wireless mesh
- Connection to home LAN and Internet
- Communication with home energy infrastructure: smart panels, DERs, EVSE, HVAC, water heaters

### Smart Panel capabilities:
- Integrated MID (Microgrid Interconnect Device)
- Revenue-grade metering on every circuit with relays
- Integrated PCS (NEC-705.13 & UL-3141)
- Local APIs: MQTT + mDNS today, Matter and OpenADR 3.1 VEN in future

---

# Smart Meter and Smart Panel Integration

### Use Cases (prioritized)
1. Meter sets Dynamic Service Rating (DSR) on Panel PCS
2. Meter subscribes to circuit power measurements from panel
3. DR events from meter to panel
4. Panel subscribes to high sample-rate waveform analysis from meter

### Protocol Options

| Protocol | Strengths | Timeline |
|----------|-----------|----------|
| **Matter** | Standard, local, appliance integration | Key clusters in 1.5-1.6 |
| **eBus** | Simple, proven (MQTT, Homie v5, mDNS) | Working today |

---

# Matter Taxonomy & Roles

### Cluster Server
- The device you want to control or read state from

### Controller (Client)
- Entity that talks to the cluster server
- Can be simple bindings (e.g., light switch controlling a bulb)

### Commissioner
- Controls pairing and owns the fabric
- Assigns Node Operational Certificates (NOCs)
- Devices with NOCs signed by the same Root CA trust each other
- Sets Access Control Lists (ACLs): which node can do what
- ACLs can be granular: specific node, specific attribute, specific endpoint

---

# Functional Control and Demand Response

- Device behavior is ultimately altered via **functional-control commands**
- Optimally translating a DR event into a functional-control command requires **detailed knowledge & context** of the customer
- The further from the customer this translation occurs, the **less context** is available
- Local optimization **cannot** occur at the grid/LSE or aggregator level

### Key Principles

- The "location" where translation occurs must be **flexible** — customer's choice
- The DR event **must** be accessible at: the device, a local HEMS, or a delegated ASP
- This translation **must not** be locked within the manufacturer's cloud

> Local HEMS is the best location to translate price & DR events to functional-control commands
