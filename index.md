---
layout: default
title: Home
---

<div class="hero" markdown="0">
  <h1>Grid Coordination</h1>
  <p>Defining the architecture of the future electric grid &mdash; through open standards, policy advocacy, and working software.</p>
</div>

The electric grid is undergoing a fundamental transformation. As homes electrify &mdash; adding EV chargers, heat pump HVAC, heat pump water heaters, battery storage, and rooftop solar &mdash; the grid must coordinate with millions of distributed loads and energy resources in real time.

**Grid Coordination** is an initiative to define, advocate for, and build the open architecture that makes this possible.

## What We Do

<div class="card-grid" markdown="0">
  <div class="card">
    <h3>Define the Architecture</h3>
    <p>We articulate how the future grid should communicate with customers and their energy management systems &mdash; through price signals and power limits, not per-device proprietary control.</p>
  </div>
  <div class="card">
    <h3>Advocate for Policy</h3>
    <p>We engage with regulators (including the California Energy Commission) to promote open standards, customer choice, and interoperability in flexible demand appliance standards.</p>
  </div>
  <div class="card">
    <h3>Practice What We Preach</h3>
    <p>We lead by example. Our founder fully electrified his home &mdash; replacing gas appliances, adding solar, battery storage, and smart panels &mdash; and <a href="/demo">demonstrated a working OpenADR 3 dynamic pricing system</a> at the CEC Demand Flexibility Summit. We now operate a <a href="https://github.com/grid-coordination/price-server-user-guide">public price server</a> delivering live California electricity prices via OpenADR 3. <a href="/presentations/whole-home-electrification.html">See the project</a>.</p>
  </div>
  <div class="card">
    <h3>Influence Standards</h3>
    <p>We contribute to standards bodies and working groups &mdash; including the <a href="https://www.openadr.org/">OpenADR Alliance</a> and AHRI 1380 &mdash; to ensure that protocols evolve to support the grid coordination architecture we envision.</p>
  </div>
  <div class="card">
    <h3>Develop Open Protocols &amp; Software</h3>
    <p>We don't just use open standards &mdash; we help create them. We proposed and led the working group that added <a href="https://github.com/grid-coordination/openadr3-specification/blob/main/doc/OpenADR3%20Object%20Operation%20Notifications%20via%20Additional%20Protocols.md">push notification protocols</a> to <a href="https://www.openadr.org/">OpenADR 3.1</a>, developed the <a href="https://ebus.energy">Electrification Bus (eBus)</a> framework for home energy infrastructure integration, and publish <a href="/software">open-source libraries</a> that make these standards practical.</p>
  </div>
</div>

## Live Price Server

<div class="card" style="border: 2px solid var(--accent); background: var(--accent-light); padding: 1.5rem; border-radius: 6px; margin: 1.5rem 0;" markdown="0">
  <h3 style="color: var(--accent); margin-top: 0;">California Electricity Prices &mdash; Live via OpenADR 3</h3>
  <p>Our free, public OpenADR 3 price server streams <strong>live California electricity prices</strong> &mdash; hourly marginal prices from the CAISO Day-Ahead Market for <strong>PG&amp;E</strong> and <strong>SCE</strong>, alongside real-time grid GHG emissions signals. Built on the open OpenADR 3.1.0 standard and accessible to any developer or application.</p>
  <p style="margin-bottom: 0.75rem;">
    <a href="https://price.grid-coordination.energy/openadr3/3.1.0/"><strong>Browse the API</strong></a> &middot;
    <a href="https://github.com/grid-coordination/price-server-user-guide"><strong>User Guide &amp; Tutorials</strong></a>
  </p>
</div>

## Home Assistant Integration

<div class="card" style="border: 2px solid var(--accent); background: var(--accent-light); padding: 1.5rem; border-radius: 6px; margin: 1.5rem 0;" markdown="0">
  <h3 style="color: var(--accent); margin-top: 0;">OpenADR 3 VEN for Home Assistant</h3>
  <p>Bring real-time electricity pricing and GHG emissions data directly into your smart home. The integration connects Home Assistant to our price server (or any OpenADR 3 VTN) and creates sensor entities that update automatically &mdash; so you can automate EV charging, HVAC, and other loads based on live prices.</p>
  <p style="margin-bottom: 0;">
    <a href="https://community.home-assistant.io/t/announcing-openadr-3-ven-for-home-assistant/1005701"><strong>Announcement &amp; Details</strong></a> &middot;
    <a href="https://github.com/grid-coordination/openadr3-ven-hass"><strong>Source &amp; Install</strong></a> &middot;
    Available via <a href="https://hacs.xyz/">HACS</a>
  </p>
</div>

## Why Now

For a century, the electric grid was engineered around **worst-case assumptions**. Distribution infrastructure was sized for peak loads that might occur only a few hours a year, because the grid had no way to talk to customer loads in real time. Coordination between generation and consumption happened at the wholesale level &mdash; customer demand was simply something the grid had to accommodate.

That constraint is gone. The same information technology that transformed every other industry &mdash; **IP networking**, **open communication protocols**, and **inexpensive networked microcontrollers and single-board computers** &mdash; now makes it practical to coordinate generation and consumption in real time, at the scale of millions of devices.

A heat pump, an EV charger, or a smart panel can each run a standards-based client on a $5 chip. A utility can publish dynamic prices and power constraints to every connected customer over the Internet. A home energy management system can optimize across every flexible load a household owns. **The grid no longer has to be built for the worst case &mdash; it can be coordinated for the actual case.**

## The Core Idea

Today's grid coordination model is fragmented: each appliance connects to its manufacturer's cloud, each aggregator controls a single device type, and no one has a holistic view of the customer's energy situation. This per-device model cannot scale to the electrified home.

The alternative is simple in principle:

1. **The grid communicates constraints** &mdash; dynamic prices (reflecting supply/demand) and power limits (protecting distribution infrastructure)
2. **A local energy management system optimizes** &mdash; across all loads and DERs, respecting both economic signals and physical limits, according to the customer's own preferences
3. **Open standards connect them** &mdash; so any EMS can work with any utility, and any appliance can work with any EMS

This is what Grid Coordination is about. Read more in our [Vision](/vision).

## OpenADR 3

We are strong proponents of [OpenADR 3](https://www.openadr.org/), the open standard for communicating demand response signals, dynamic pricing, and grid events from utilities to customers. OpenADR 3 provides the protocol layer that connects utility price servers to customer energy management systems &mdash; a critical piece of the grid coordination architecture.

Our open-source [software libraries](/software) implement OpenADR 3 in both Clojure and Python, and our [VTN server](https://github.com/grid-coordination/clj-oa3-vtn) powers the [live price server](#live-price-server) serving real California electricity prices to anyone with a standard OpenADR 3 client.

## This Is Not Theoretical

Pacific Gas & Electric, California's largest utility, is [piloting smart meters and meter-mounted smart panels that coordinate directly with home energy devices](https://www.canarymedia.com/articles/utilities/as-californians-electrify-tech-prevent-grid-overload) &mdash; enforcing transformer-level power limits so customers can electrify without panel upgrades or costly grid reinforcement. The architecture described on this site is being built and deployed today. See [Resources](/resources) for more.
