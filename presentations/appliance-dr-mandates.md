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

# Mandates for Appliance Support for
# Demand-Response, Energy-Shifting &
# Power-Control Functionality

**Why CTA-2045 has failed, and what we should do going forward**

DC Jackson

---

# What Should the Policy Goal Be?

### What
Provide the capability for high-load appliances (SGDs) to:
- Curtail (or encourage) power consumption
- Shift energy usage

### Cost
Provide demand flexibility **affordably**, allocating costs thoughtfully:
- Adding controls to appliances adds both unit (hardware) and development (NRE) costs

### Control
Provide DR management wherever needed to maximize grid benefits:
- LSE / Utility
- Demand Response Provider (DRP)
- Appliance owner, via local **Home Energy Management System** (HEMS)

---

# Ensured vs. Enabled

<div class="columns">
<div>

### Ensured
The appliance supports:
- An open/standard protocol for flexible demand control
- Server URL is customer-configurable
- Network interface(s) for LAN/Internet

**Fully capable — no additional cost or effort!**

</div>
<div>

### Enabled
The appliance supports:
- A connector/port for another device
- That device provides flexible demand control by unspecified means

**Requires additional cost and effort...**

</div>
</div>

---

# CTA-2045: Components and How It Works

### SGD (Appliance)
- CTA-2045 SGD interface
- Microcontroller

### UCM (Communications Module)
- CTA-2045 UCM interface
- Network interface: Wi-Fi, cellular, Ethernet
- Proprietary protocol to DRP
- Microcontroller

**CTA-2045 *enables* flexible demand control — it doesn't *ensure* it.**

---

# How CTA-2045 Addresses Policy Goals

| Goal | How CTA-2045 Addresses It |
|------|---------------------------|
| **What** | Standard port on appliances; aftermarket UCM connects |
| **Cost** | Manufacturer absorbs port cost; DRP pays for UCM, recoups via reduced incentives |
| **Control** | UCM connects to DRP via Internet using proprietary protocol |

### Limitations
- UCM typically specific/tied to a single DRP
- No end-user ability to control appliance locally
- No standard protocol between UCM and DRP

---

# CTA-2045 Water Heater Enrollment: The Data

> "As of March 2025, comprehensive data on the exact percentage of CTA-2045-enabled water heaters actively participating in DR programs is limited"

- The percentage of enrolled & connected CTA-2045 water heaters is **far closer to 0% than 100%**
- This connection percentage is **unlikely to materially change**

### Conclusion

CTA-2045 mandates have **failed** to accomplish the goal of shifting water heater energy usage.

**Worse:** Manufacturers must include CTA-2045 for mandated markets, consuming the "budget" for device communications — **precluding** incorporation of better solutions.

> Continuing to mandate CTA-2045 is PREVENTING increased flexible-demand appliance participation.

---

# What Went Wrong with CTA-2045?

Ex-ante it seemed like a great idea, and everyone had the best intentions...

1. CTA-2045 only **enables** connection via a UCM obtained and installed separately
2. UCM must be configured to home Wi-Fi — technically challenging for many
3. UCMs are expensive: **~$100-150+**
4. **No standard protocol** between UCM and DRP — increases cost for DR providers
5. The cost & effort to bridge from *enabled* to *ensured* was **too large**

### The world has changed since CTA-2045 was developed:
- Appliances now include microcontrollers and network interfaces at low cost
- Vast majority of households have Internet and Wi-Fi

---

# The Proposed Solution

Many/most new water heaters now include Wi-Fi for manufacturer cloud connectivity.

### Requirements:
1. SGDs with network interfaces **must** support an open standard protocol for DR
2. SGDs **must** support/integrate **OpenADR 3.1**
   - Adds no/little incremental hardware cost to appliances with existing Wi-Fi
3. SGDs **must** provide a **USB-C** connector for additional network interfaces
4. OpenADR 3.1 VTN URL **must** be customer-configurable
5. OpenADR 3.1 becomes the standard protocol for LSE/DRP communication

**No UCM needed — saving cost to both homeowner and DR provider.**

> The exact same solution works for HVAC and EVSE.

---

# What About Dynamic Prices?

- Increasing agreement that **highly dynamic pricing** is better than legacy DR events for shifting energy usage
- **OpenADR 3** fully supports communication of dynamic prices from grid/LSE to appliance and/or local HEMS
- OpenADR 3 provides **both** conventional DR events **and** dynamic prices

> CTA-2045-B has no support for dynamic prices. "Peak price" doesn't count.

---

# Proposed Requirements for Future Mandates

### SGDs must:
- Support connection to the home network
- Integrate at least one network interface (Wi-Fi)
- Provide a USB-C port for additional interfaces (cellular, Ethernet)
- Support **OpenADR 3.1** (or later)
- Support customer configuration of the OpenADR VTN URL

### Enabling customer choice of connection to:
- DRP
- LSE
- Local Home Energy Management System (HEMS)

---

# What About Matter?

- Matter excels at smart-appliance interoperability **within** the home
- Does **not** provide utility-to-customer coordination alone
- Combined with OpenADR 3.1: HEMS uses Matter for local device control

### The Best of Both Worlds

| Protocol | Role |
|----------|------|
| **OpenADR 3.1** | Grid-to-home: prices, DR events, power limits |
| **Matter DEM** | Within-home: device energy management |

> Requiring BOTH OpenADR 3.1 and Matter energy management would provide consumers the most choice and flexibility.

---

# DR Protocol Options

| Requirement | What It Achieves |
|------------|-----------------|
| Require **OpenADR 3.1** | **Ensures** SGDs can directly receive DR events and dynamic prices |
| Require **Matter DEM** | **Enables** SGDs to be managed by consumer's HEMS |
| Require **both** | Maximum choice and flexibility for innovative energy solutions |

---

# Addressing Objections

### "Manufacturers want proprietary cloud control"
- Limits consumer choice of DRP
- Reduces economic benefit to consumer
- Consumers with multiple SGDs shouldn't be forced to use DRPs
- Consumers cannot manage SGDs locally via HEMS

### The fix:
Even if manufacturers integrate OpenADR 3.1, they **must also** enable the homeowner to configure the VTN URL — giving the customer the choice.

---

# Wi-Fi Reliability Concerns

### Obstacles experienced with Wi-Fi-connected UCMs:
- Wi-Fi may not reach water heater location (garage, basement)
- Configuring UCM to Wi-Fi is technically challenging
- SSID/password changes disconnect the UCM silently
- Cybersecurity objections from some customers

### Solution: Ethernet for stationary appliances
- Water heaters, HVAC, and EVSE are **not mobile**
- Incentivize Ethernet connections during installation
- Amend building codes to require Ethernet near high-amperage outlets

> ~92% of US households have Internet. Equity issues should be addressed via assistance programs, as with electric service.

---

# CTA-2045 Mandates Today

| Jurisdiction | Status |
|-------------|--------|
| **Washington** | Required since Jan 1, 2021 (RCW 19.260.080) |
| **Oregon** | Required since Jul 1, 2023 (HB 2062, delayed from Jan 2022) |
| **Colorado** | Considering similar requirements |
| **Federal** | S. 4061 / HR 7962 directed DOE to evaluate by end of 2024 |

These mandates have produced near-zero participation rates.

> It is time to move from *enabling* demand flexibility to *ensuring* it — with open protocols built into the appliance.
