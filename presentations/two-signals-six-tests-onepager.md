---
marp: true
paginate: false
---

<h1>Two signals, six tests</h1>
<p class="sub">The grid has two problems. Few proposals solve even one.</p>
<p class="by"><strong>DC Jackson</strong> &middot; grid-coordination.energy &middot; August 2026</p>

<div class="hr"></div>

<div class="sec">
<h2>The frame</h2>
<p>The grid has two different problems and they need two different signals. <strong>Balancing the state is an economics problem:</strong> the right signal is a price that changes hourly or faster, and it moves energy across time. <strong>Protecting the wire to one house is a physics problem:</strong> the right signal is a limit on that customer's whole service connection, import and export, and it caps power immediately. You cannot solve a physics problem with a price, and you cannot motivate flexibility with a limit.</p>
</div>

<div class="sec">
<h2>The six tests</h2>
<div class="cols2">

<div class="t"><span class="q">1. Does the grid send the home <i>an objective</i>, or does it operate the appliance?</span>
<span class="pf"><b class="p">PASSES</b> an hourly price and a connection limit, published to everyone. <b class="f">FAILS</b> a program that needs the ability to command a named appliance in a named house.</span></div>

<div class="t"><span class="q">2. Does the open interface reach <i>the appliance itself</i>, or stop at the manufacturer's cloud?</span>
<span class="pf"><b class="p">PASSES</b> the appliance speaks the open interface itself, over ordinary networking. <b class="f">FAILS</b> an appliance that complies only through a cloud service the manufacturer can switch off.</span></div>

<div class="t"><span class="q">3. Can the customer <i>point the appliance at a server of their own choosing?</i></span>
<span class="pf"><b class="p">PASSES</b> the server address is a setting the owner can change, without the manufacturer's app, account or permission. <b class="f">FAILS</b> a default that is a lock.</span></div>

<div class="t"><span class="q">4. Can the customer take the signal <i>directly from their utility,</i> or is a middleman required?</span>
<span class="pf"><b class="p">PASSES</b> a tariff any customer can take without enrolling with a third party; aggregators fully supported, never required. <b class="f">FAILS</b> flexibility reachable only by signing with one company.</span></div>

<div class="t"><span class="q">5. Does the limit <i>hold at the customer's connection,</i> when the internet does not?</span>
<span class="pf"><b class="p">PASSES</b> one limit for the entire connection, advisory to the home so it can plan, enforced at the connection so it binds rather than being hoped for, retained locally when the network is gone. <b class="f">FAILS</b> a resource that evaporates during a public safety power shutoff.</span></div>

<div class="t"><span class="q">6. Does the customer <i>who cannot respond</i> end up better off, or worse?</span>
<span class="pf"><b class="p">PASSES</b> a signal that is free, public, identical for everyone, and readable by the cheapest device in the house. <b class="f">FAILS</b> flexibility that requires a credit relationship and a contract.</span></div>

</div>
</div>

<div class="sec">
<div class="box"><strong>The drafting rule.</strong> Name the capability in the rule, and the standard in an appendix you can update without reopening the rule. Write it at the appliance, not at somebody's server.</div>
</div>

<div class="sec">
<h2>Three levers, all in proceedings already open</h2>
<div class="cols3 lev">
<div><h3>CPUC</h3><p>Attach an open-access condition to the flexible service connection ordered in <strong>D.26-02-025</strong>: the limit must reach the customer in an open, machine-readable form their own equipment can read directly, with no enrollment and no intermediary. That is Question 8 of the July 7, 2026 ruling in R.21-06-017, answered. Extend the standard offer beyond PG&amp;E and SCE. Require tariffs published in a machine-readable, computable form (the open <strong>URPX</strong> standard does this), so any rate becomes a price stream, and retire attributes a stream cannot carry, such as demand charges.</p></div>
<div><h3>CEC</h3><p>The one adopted standard, pool controls, writes a fixed daily schedule into the rule and requires no ability to receive a price, a signal or a limit. Do not repeat that in the three still open. In the standards now in pre-rulemaking for thermostats, EV charging equipment and home batteries, make <strong>tests 2, 3 and 5</strong> explicit functional requirements. The hourly rate is due January 1, 2027; the tool that lets a device find which rate a customer is on is not due until May 8, 2029.</p></div>
<div><h3>The Legislature</h3><p><strong>AB 1787</strong> is held in Senate Appropriations. It has been carried once, so it can be carried again, and it is one clause short: it gives customers access to their <strong>data</strong>. Add access to the <strong>signals</strong>, and the right to point their own equipment at a server of their choosing. Oversight question: how much of the flexibility ratepayers have already paid for depends on a private company continuing to run a cloud service?</p></div>
</div>
</div>

<div class="foot">
<strong style="color:#16212E">This is running today.</strong> A free, public server carries real hourly California day-ahead prices for PG&amp;E and SCE territory, plus grid emissions, on the open OpenADR&nbsp;3 standard. No account, no contract, no enrollment: <strong style="color:#2A6E3F">price.grid-coordination.energy</strong>. Open-source home software reads it and acts on it.<br>
<strong style="color:#16212E">The offer.</strong> Tell me which of your open proceedings this belongs in and I will file it as comments this month, in whatever format the proceeding needs, at no charge. Or one workshop: I will bring the running system and you can try to break it.
</div>
