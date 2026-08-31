---
layout: default
title: Home
---

<div class="hero" markdown="0">
  <h1>Grid Coordination</h1>
  <p>The grid has two problems. They need two different signals, and today the customer receives neither one directly.</p>
</div>

## Two problems, not one

![The whole state hour by hour, an economics problem answered by a price; and one block right now, a physics problem answered by a limit](/images/diagrams/two-problems.svg)

The grid has to do two different things at once, and they are not the same job.

**Balancing the state, hour by hour, is an economics problem.** Supply must match demand continuously. The right signal is a price that changes hourly or faster, and it moves energy through the day. California is already moving here, and it should be pursued harder, not hedged.

**Protecting the wire to one house is a physics problem.** The neighborhood transformer and the service drop have a fixed capacity, and they do not care what electricity costs. The right signal is a limit on that customer's whole service connection, import and export, and it caps power immediately.

**Both land on the bill.** Peak we cannot shift is generation and transmission somebody has to build; a transformer we cannot protect is a street somebody has to dig up. Ratepayers fund both.

You cannot solve a physics problem with a price, and you cannot motivate flexibility with a limit. Read the full argument in our [Vision](/vision).

## What that means in practice

Today's model is fragmented. Each appliance connects to its manufacturer's cloud, each aggregator controls a single device type, and nobody has a view of the whole house. That cannot scale to the electrified home, where one household has an EV charger, a heat pump, a heat pump water heater, battery storage and rooftop solar all at once.

The alternative is simple in principle:

1. **The grid communicates constraints** &mdash; a dynamic price reflecting supply and demand, and a power limit protecting distribution infrastructure
2. **A local energy management system optimizes** &mdash; across all loads and resources, respecting both signals, according to the customer's own preferences
3. **Open standards connect them** &mdash; so any energy manager works with any utility, and any appliance works with any energy manager

**This is not speculative in California.** In February 2026 the CPUC directed PG&amp;E and SCE to establish a standardized, tariffed flexible service connection (D.26-02-025), with load managed behind a certified power control system excluded from the connected load calculation: a customer-level power limit, in a tariff. See [Policy](/policy) for the regulatory record.

## This is running today

<div class="card" style="border: 2px solid var(--accent); background: var(--accent-light); padding: 1.5rem; border-radius: 6px; margin: 1.5rem 0;" markdown="0">
  <p>A <a href="https://github.com/grid-coordination/price-server-user-guide"><strong>free, public OpenADR 3 price server</strong></a> streams real hourly California electricity prices and grid emissions: CAISO Day-Ahead prices for PG&amp;E and SCE, prices computed from published SDG&amp;E, LADWP and City of Palo Alto rate schedules, and marginal emissions for 11 grid regions. <strong>No account, no contract, no enrollment.</strong></p>
  <p>An <a href="https://github.com/grid-coordination/openadr3-ven-hass"><strong>open-source Home Assistant integration</strong></a>, in the HACS default repository, receives that signal and orchestrates the household's loads against it.</p>
  <p style="margin-bottom: 0;">
    <a href="/demo"><strong>See the working demonstration</strong></a> &middot;
    <a href="https://price.grid-coordination.energy/openadr3/3.1.0/programs?limit=5"><strong>Try the API</strong></a> &middot;
    <a href="/software"><strong>Open-source libraries</strong></a>
  </p>
</div>

<a href="/demo"><img src="/images/photos/openadr3-demo-board.jpg" alt="The demonstration board: an OpenADR 3 price server in the cloud, a Home Assistant gateway inside a house outline, and tablets showing an EV charger, water heater and HVAC unit each responding to the current hourly price"></a>

<p class="caption">The complete grid-to-appliance system, demonstrated at the 2026 CEC/EPRI Electrification Summit. Every screen is live.</p>

## Start here

<div class="card" style="border: 2px solid var(--accent); background: var(--accent-light); padding: 1.5rem; border-radius: 6px; margin: 1.5rem 0;" markdown="0">
  <h3 style="color: var(--accent); margin-top: 0;">Two Signals, Six Tests</h3>
  <p>Prepared for California PUC and CEC staff. The two problems, the two signals that answer them, and six tests for judging any flexibility proposal that crosses your desk.</p>
  <p style="margin-bottom: 0;">
    <a href="/presentations/two-signals-six-tests.html"><strong>View the slides</strong></a> &middot;
    <a href="/presentations/two-signals-six-tests.pdf"><strong>PDF</strong></a> &middot;
    <a href="/presentations/two-signals-six-tests-onepager.pdf"><strong>One-page handout</strong></a>
  </p>
</div>

## Why now

For a century the grid was engineered around **worst-case demand**, because it had no way to talk to customer loads in real time. Infrastructure was oversized, and customer consumption was simply something the grid had to accommodate.

That constraint is gone. A heat pump, an EV charger or a smart panel can each run a standards-based client on a $5 chip. A utility can publish dynamic prices and power limits to every connected customer over the Internet. **The grid no longer has to be built for the worst case. It can be coordinated for the actual case.**

## What we do

<div class="card-grid" markdown="0">
  <div class="card">
    <h3>Advocate for policy</h3>
    <p>We file formal comments with the California Energy Commission on flexible demand appliance standards, arguing for open standards, customer choice and interoperability. <a href="/policy">Our filings and the regulatory record</a>.</p>
  </div>
  <div class="card">
    <h3>Build open protocols and software</h3>
    <p>We proposed and led the working group that added <a href="https://github.com/grid-coordination/openadr3-specification/blob/main/doc/OpenADR3%20Object%20Operation%20Notifications%20via%20Additional%20Protocols.md">push notifications</a> to <a href="https://www.openadr.org/">OpenADR 3.1</a>, and publish <a href="/software">open-source libraries</a> in Clojure and Python.</p>
  </div>
  <div class="card">
    <h3>Practice what we preach</h3>
    <p>Our founder fully electrified his home, then built and now operates the public price server and the demonstration system above. <a href="/presentations/whole-home-electrification.html">See the project</a>.</p>
  </div>
</div>

<p style="margin-top:2rem"><a href="/vision"><strong>Vision</strong></a> &middot; <a href="/policy"><strong>Policy</strong></a> &middot; <a href="/standards"><strong>Standards</strong></a> &middot; <a href="/software"><strong>Software</strong></a> &middot; <a href="/demo"><strong>Demo</strong></a> &middot; <a href="/presentations/"><strong>Presentations</strong></a> &middot; <a href="/resources"><strong>Resources</strong></a></p>
