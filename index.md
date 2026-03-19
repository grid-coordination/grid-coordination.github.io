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
    <h3>Influence Standards</h3>
    <p>We contribute to standards bodies and working groups to ensure that protocols like <a href="https://www.openadr.org/">OpenADR 3</a> evolve to support the grid coordination architecture we envision.</p>
  </div>
  <div class="card">
    <h3>Build Open Software</h3>
    <p>We develop and publish open-source libraries that implement these standards, making it practical for developers to build grid-coordinated applications today.</p>
  </div>
  <div class="card">
    <h3>Practice What We Preach</h3>
    <p>We lead by example. Our founder fully electrified his home &mdash; replacing gas appliances, adding solar, battery storage, and smart panels &mdash; to demonstrate that whole-home electrification is practical, affordable, and better in every way. <a href="/presentations/whole-home-electrification.html">See the project</a>.</p>
  </div>
</div>

## The Core Idea

Today's grid coordination model is fragmented: each appliance connects to its manufacturer's cloud, each aggregator controls a single device type, and no one has a holistic view of the customer's energy situation. This per-device model cannot scale to the electrified home.

The alternative is simple in principle:

1. **The grid communicates constraints** &mdash; dynamic prices (reflecting supply/demand) and power limits (protecting distribution infrastructure)
2. **A local energy management system optimizes** &mdash; across all loads and DERs, respecting both economic signals and physical limits, according to the customer's own preferences
3. **Open standards connect them** &mdash; so any EMS can work with any utility, and any appliance can work with any EMS

This is what Grid Coordination is about. Read more in our [Vision](/vision).

## OpenADR 3

We are strong proponents of [OpenADR 3](https://www.openadr.org/), the open standard for communicating demand response signals, dynamic pricing, and grid events from utilities to customers. OpenADR 3 provides the protocol layer that connects utility price servers to customer energy management systems &mdash; a critical piece of the grid coordination architecture.

Our open-source [software libraries](/software) implement OpenADR 3 in both Clojure and Python.
