---
layout: default
title: Policy
permalink: /policy
---

# Policy & Advocacy

Grid Coordination engages with regulators and standards bodies to promote an open, customer-centric architecture for the electrified grid. Our advocacy rests on four principles:

## The Technology Moment

The grid was historically engineered around **worst-case demand** because real-time coordination with customer loads was impossible. Infrastructure was oversized; customer consumption was whatever it happened to be. That is no longer a fundamental constraint. **IP networking**, **open grid-coordination protocols**, and **low-cost networked microcontrollers and single-board computers** now make it practical to communicate dynamic prices and power limits to every flexible load in every home &mdash; and for those loads to respond autonomously on the customer's behalf.

Regulation's role is to ensure this new coordination layer stays **open** &mdash; so the capability benefits customers rather than entrenching proprietary lock-in.

## Core Principles

### Customer Choice

Customers should control which devices they use and which services they delegate control to. A customer should be able to use the energy management system of their choosing to coordinate all the flexible loads in their home. No appliance manufacturer should be able to lock customers into proprietary control ecosystems.

### Interoperability

Any control application should work with any appliance. A customer should be able to switch HVAC systems without changing their control interface, or switch energy management platforms without replacing their appliances. This requires open, standard protocols &mdash; not proprietary cloud integrations.

### Open Standards via Regulation

History shows that open standards in energy do not emerge from market forces alone. HVAC manufacturers have moved *away* from open control interfaces toward proprietary lock-in. By contrast, the water heater industry demonstrates what regulation can achieve: Washington, Oregon, Colorado and New York mandated the CTA-2045/EcoPort standard, and manufacturers responded by including it broadly &mdash; because supporting one standard SKU became cheaper than managing regional variants.

### Access to Your Own Meter

A customer has a right to the real-time data their own meter produces, locally, as it is generated. Not a next-day download from a utility portal, and not a summary mediated by whoever the utility picked to administer a program. Real-time local access is what makes autonomous response possible: an energy management system cannot manage what it cannot see, and the meter is the only point where the whole site's import and export is actually measured. The same right must extend to a third party the customer authorizes, chosen by the customer. The same argument applies to the tariff itself: rates should be published in a machine-readable, computable form, which is what the open [Utility Rate Plan Exchange (URPX)](https://lfenergy.org/projects/utility-rate-plan-exchange-urpx/) standard, hosted by LF Energy, is built for.

**Open standards enforced through regulation create the conditions for innovation, competition, and customer benefit.**

## Regulatory Engagement

### Briefing materials

- **[Two Signals, Six Tests](/presentations/two-signals-six-tests.html)** &mdash; prepared for California PUC and CEC staff. The two problems, the two signals that answer them, and six tests for judging any flexibility proposal. [PDF](/presentations/two-signals-six-tests.pdf) &middot; [one-page handout](/presentations/two-signals-six-tests-onepager.pdf).

### California Energy Commission &mdash; Flexible Demand Appliance Standards

We have contributed formal responses to CEC proceedings on flexible demand standards:

- **[Docket 24-FDAS-03](/policy/24-fdas-03)** &mdash; Low-Voltage Thermostats: We advocated for broadening the scope beyond thermostats to encompass HVAC systems holistically, requiring open control protocols, and supporting (but not requiring) aggregators.

- **[Docket 24-FDAS-04](/policy/24-fdas-04)** &mdash; Electric Vehicle Supply Equipment: We advocated for customer choice and interoperability in EVSE standards, open protocol requirements for local and cloud control, V2X capability requirements, and user-configurable flexible demand servers.

### Key Regulatory Drivers

The regulatory landscape in California is moving toward the grid coordination architecture we advocate:

| Driver | Status | Significance |
|--------|--------|-------------|
| **[CalFUSE](https://www.cpuc.ca.gov/-/media/cpuc-website/divisions/energy-division/documents/demand-response/demand-response-workshops/advanced-der---demand-flexibility-management/ed-white-paper---advanced-strategies-for-demand-flexibility-management.pdf)** | Staff white paper, June 2022 | CPUC's California Flexible Unified Signal for Energy: the roadmap toward a single, universally available dynamic price signal. A framework, not a decision or a program |
| **[CEC Load Management Standards](https://www.energy.ca.gov/programs-and-topics/topics/load-flexibility/load-management-standards)** | Adopted, in force | Large IOUs must make at least one hourly, marginal cost-based rate available to every customer class by January 1, 2027. Large CCAs must offer that rate or a qualifying flexibility program by July 1, 2027. Covered rates must be published in the state's free public rate database, though the joint access tool that would make it usable is not due until May 8, 2029 (CEC Order 26-0312-03b) |
| **[CPUC demand flexibility rate design](https://www.cpuc.ca.gov/news-and-updates/all-news/cpuc-issues-guidance-for-utility-dynamic-hourly-rates)** (D.25-08-049) | Decided August 2025; rates still in testimony | Adopted guidelines for how PG&E, SCE, and SDG&E design hourly demand flexibility rates. The guidelines are settled; the rates themselves are not yet approved. Remaining rate design issues moved to R.26-04-009, opened April 2026 |
| **CPUC flexible service connections** (D.26-02-025) | Decided February 2026 | Directs PG&E and SCE to establish a standardized, tariffed flexible service connection, so a customer can energize now under a defined, limited load profile instead of waiting on an upstream upgrade. Load managed behind a certified power control system is excluded from the connected load calculation. **California has already put a customer-level power limit into a tariff** |
| **[CEC Flexible Demand Appliance Standards](https://www.energy.ca.gov/proceedings/active-proceedings/flexible-demand-appliances)** | One adopted; three in pre-rulemaking | Pool controls are adopted, for units manufactured on or after September 29, 2025: the first flexible demand appliance standard in the nation. Low-voltage thermostats, EV supply equipment, and battery storage are open information-gathering dockets with no proposed rule text |
| **[CA AB 1787](https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202520260AB1787)** | **Pending.** Held under submission in Senate Appropriations, August 13, 2026 | Not law, but it points the right direction, and it establishes that the Legislature is willing to take this up. It would condition cost recovery for the next smart meter upgrade on customers being able to read their own meter data directly and as it is generated, and to authorize a third party of their choosing to read it too. **It has been carried once and it can be carried again** |

We do not only argue for this architecture, we operate it. A [free, public OpenADR 3 price server](https://github.com/grid-coordination/price-server-user-guide) carries real hourly California prices and grid emissions with no account and no enrollment, a [Home Assistant integration](https://github.com/grid-coordination/openadr3-ven-hass) consumes it in the home, and the [open-source libraries](/software) behind both are published for anyone to use.

These actions are converging on the architecture we describe in our [Vision](/vision): dynamic pricing as the primary demand response mechanism and a per-customer power limit as the protection for distribution infrastructure, both delivered through open standards, with local energy management systems optimizing autonomously on behalf of customers. What is settled is the direction. What is not yet settled is whether a customer will be able to participate without a middleman, and that is decided over the next eighteen months.
