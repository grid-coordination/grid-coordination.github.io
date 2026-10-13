---
marp: true
paginate: true
footer: 'grid-coordination.energy<span class="who">DC Jackson</span>'
style: |
  :root {
    --ink: #16212E;
    --body: #2C3844;
    --muted: #7A8592;
    --hair: #D9DEE3;
    --paper: #FFFFFF;
    --alt: #F3F5F2;
    --green: #2A6E3F;
    --green-l: #E6EFE8;
    --copper: #B25B27;
    --copper-l: #F7EBE2;
  }
  section {
    font-family: "Avenir Next", Avenir, -apple-system, "Helvetica Neue", Arial, sans-serif;
    background: var(--paper);
    color: var(--body);
    font-size: 25px;
    line-height: 1.45;
    padding: 60px 76px 72px;
    letter-spacing: -0.1px;
  }
  section.alt   { background: var(--alt); }
  section.tight h2 { font-size: 32px; }
  section.tight h3 { margin-bottom: .7em; }
  section.dense table { font-size: 17.5px; }
  section.dense2 li { padding: 8px 0; font-size: 19px; }
  section.dense2 .band { font-size: 19px; padding: 13px 18px; }
  section.dense2 .columns { gap: 1.8rem; }
  section.dense table td { padding: 8px 18px 8px 0; }
  section.dark  { background: var(--ink); color: #EEF1F4; }
  section.dark h1, section.dark h2, section.dark strong { color: #FFFFFF; }
  section.dark h3 { color: #8FA89A; }
  section.dark .big, section.dark .huge { color: #FFFFFF; }
  section.dark .muted, section.dark em, section.dark .cap { color: #9BAAB6; }
  section.dark blockquote { color: #FFFFFF; border-left-color: #6E9E7C; }
  section.dark li { border-color: #33414F; }
  section.dark table td { border-bottom-color: #33414F !important; }
  section.dark table th { color: #9BAAB6; border-bottom-color: #6E8090 !important; }

  h1 { font-size: 56px; font-weight: 600; letter-spacing: -1.5px; line-height: 1.06; color: var(--ink); margin: 0 0 .3em; }
  h2 { font-size: 37px; font-weight: 600; letter-spacing: -0.8px; line-height: 1.12; color: var(--ink); margin: 0 0 .55em; }
  h3 { font-size: 15px; font-weight: 600; letter-spacing: 2.6px; text-transform: uppercase; color: var(--green); margin: 0 0 1em; }
  h4 { font-size: 21px; font-weight: 600; color: var(--ink); margin: 0 0 .3em; }
  strong { font-weight: 600; color: var(--ink); }
  em { font-style: normal; color: var(--muted); }
  a { color: var(--green); text-decoration: none; border-bottom: 1px solid rgba(42,110,63,.35); }
  .cap a, .band a { color: var(--green); }

  section ul { list-style: none; padding-left: 0; margin: 0; }
  section li { padding: 13px 0; border-top: 1px solid var(--hair); }
  section li:last-child { border-bottom: 1px solid var(--hair); }
  section ol { padding-left: 0; margin: 0; counter-reset: t; list-style: none; }
  section ol li { padding: 12px 0 12px 52px; position: relative; }
  section ol li::before { counter-increment: t; content: counter(t);
    position: absolute; left: 0; top: 12px; width: 30px; height: 30px; border-radius: 15px;
    background: var(--green); color: #fff; font-size: 16px; font-weight: 600;
    display: flex; align-items: center; justify-content: center; }

  section table { display: table; border-collapse: collapse; width: 100%; font-size: 21px; margin: 1.1em 0 0; }
  section table th, section table td { border: 0 !important; background: transparent; }
  section tbody tr:nth-child(odd), section tbody tr:nth-child(even) { background: transparent; }
  section table th { font-size: 14px; font-weight: 600; letter-spacing: 2px; text-transform: uppercase;
    color: var(--ink); text-align: left; border-bottom: 1.5px solid var(--ink) !important; padding: 0 20px 11px 0; }
  section table td { border-bottom: 1px solid var(--hair) !important; padding: 12px 20px 12px 0; vertical-align: top; }

  section blockquote { border: none; border-left: 3px solid var(--green); margin: 0; padding: 4px 0 4px 30px;
    color: var(--ink); font-size: 30px; line-height: 1.3; background: transparent; }
  section blockquote::before, section blockquote::after { content: none; }

  header, footer { color: var(--muted); font-size: 13px; letter-spacing: 1.4px; text-transform: uppercase; }
  footer { width: 100%; box-sizing: border-box; }
  footer .who { position: absolute; left: 0; right: 0; text-align: center; }
  section::after { color: var(--muted); font-size: 15px; }

  section img { display: block; margin: 0 auto; }
  .columns  { display: grid; grid-template-columns: 1fr 1fr; gap: 2.4rem; }
  .columns3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1.9rem; }
  .columns4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 26px; }
  .columns4.lever { font-size: 17px; line-height: 1.4; }
  .columns4.lever h4 { font-size: 18px; }
  .big   { font-size: 38px; font-weight: 500; line-height: 1.22; letter-spacing: -0.8px; color: var(--ink); }
  .huge  { font-size: 47px; font-weight: 600; line-height: 1.14; letter-spacing: -1.2px; color: var(--ink); }
  .muted { color: var(--muted); }
  .green { color: var(--green); font-weight: 600; }
  .copper{ color: var(--copper); font-weight: 600; }
  .green strong, .copper strong { color: inherit; }
  .cap   { font-size: 18px; color: var(--muted); letter-spacing: 0; line-height: 1.4; margin-top: 14px; }
  .ask   { font-size: 21px; color: var(--ink); font-weight: 600; line-height: 1.36; margin-top: 16px; }
  .rule  { height: 1px; background: var(--hair); margin: .9em 0; }
  .center{ text-align: center; }
  .pf    { font-size: 20px; margin-top: 18px; line-height: 1.5; }
  .pf .p { color: var(--green); font-weight: 600; }
  .pf .f { color: var(--copper); font-weight: 600; }
  .band  { background: var(--green-l); border-left: 3px solid var(--green); padding: 16px 22px; font-size: 21px; }
  .band p, .bandc p { margin: 0 0 .5em; }
  .band p:last-child, .bandc p:last-child { margin-bottom: 0; }
  .bandc { background: var(--copper-l); border-left: 3px solid var(--copper); padding: 16px 22px; font-size: 21px; }
  .lever h4 { color: var(--green); font-size: 19px; letter-spacing: 0; }
  .lever { font-size: 19px; line-height: 1.42; }
  .lever p { margin: 0 0 .5em; }
  .do { color: var(--green); font-weight: 600; }
  .cta   { background: var(--ink); color: #FFFFFF; padding: 20px 28px 22px; border-radius: 6px;
           font-size: 22px; line-height: 1.4; margin-top: 6px; }
  .cta p { margin: 0; color: #E7ECF0; }
  .cta strong { color: #FFFFFF; }
  .cta .lbl { display: block; font-size: 13px; font-weight: 600; letter-spacing: 2.8px;
              text-transform: uppercase; color: #7FB894; margin-bottom: 9px; }
---

<!-- _class: alt -->
<!-- _paginate: false -->
<!-- _footer: "" -->

### Connected Home Energy Forum &middot; Berlin, 26 October 2026

# Electrification without<br>interoperability

<div class="cap" style="margin-top:28px">

DC Jackson &middot; Grid Coordination &middot; grid-coordination.energy

</div>

---

## Electrification creates two problems. Today we are solving one.

![w:940](../images/diagrams/two-problems.svg)

<div class="cap">

Balancing the grid is an <span class="green">economics</span> problem. Protecting the transformer is a <span class="copper">physics</span> problem. **Both land on the customer's bill.** Peak we cannot shift is generation and transmission somebody has to build; a transformer we cannot protect is a street somebody has to dig up.

</div>

---

## One signal cannot do both jobs

| | A dynamic price | A per-customer power limit |
| --- | --- | --- |
| **What it is** | What energy costs right now | How much power this connection may draw right now |
| **Unit** | The entire grid | One service connection |
| **What it solves** | Balancing the grid | Protecting the transformer |
| **What it does** | Moves energy across time | Moves nothing. Caps power, immediately |
| **Without it** | Nobody has a reason to shift | Nothing stops everyone shifting at once |

<div class="cap">

A price is an incentive shared by everyone on the same asset. It cannot stop five houses on one transformer responding to the same number at the same moment. **A price is an incentive over a group. A limit is an obligation on one connection.**

</div>

---

<!-- _class: dense2 -->

### WHAT THE DISTRIBUTION NETWORK IS ALREADY DOING

## We are already experiencing the transformer problem

- **Voltage rises on a sunny afternoon**, and inverters and chargers trip off to protect themselves. The customer sees a fault, not a grid condition.
- **Connections are refused, queued or derated** for heat pumps and chargers, because nobody can promise what a house will draw at the worst moment.
- **Capacity is managed by curtailment and by waiting**, because there is no signal that tells a connection how much it may take right now.

<div class="band">

Every one of these is about protecting the transformer. **No signal in use today carries an answer to them.**

</div>

---

## The good news: three standards already carry a price

| | Carries a price today |
| --- | --- |
| **OpenADR 3** | Utility to the customer's own equipment, over the Internet |
| **Matter** | The Commodity Price cluster, inside the home |
| **EEBUS** | Time of Use Tariff: "the absolute price SHALL be included", currency per Wh |

<div class="cap">

Tomorrow you will hear from Matter and from OpenADR on exactly this. **This half of the problem has an answer.**

</div>

---

<!-- _class: dense2 -->

### NOT A PROPOSAL. A RUNNING SERVICE.

## A free, public price server, no account required

- **About 1,700 programs.** Real hourly prices for two large utilities across 105 distribution circuits and substations, plus prices computed from published rate schedules.
- **Hourly marginal carbon, for 11 grid regions**, on the same server, in the same shape. A greenhouse-gas number is price-shaped: a device optimizes against it exactly as it does a price.
- **No authentication, no contract, no enrollment.** Open-source home automation receives it and orchestrates the house against it.

<div class="band">

**`price.grid-coordination.energy/openadr3/3.1.0/programs?limit=5`**<br>Try it in a browser during the break.

</div>

---

<!-- _class: dense -->

## Three standards already define a connection limit

| | A connection-level import/export limit |
| --- | --- |
| **OpenADR 3** | Yes, as event payloads |
| **EEBUS** | **Power Envelope**, defined at "the building's grid connection point", import and export, time-varying, with a declared fallback |
| **Matter** | A power threshold is defined in the Application Cluster specification |

---

<!-- _class: dense2 -->

## We know how to do this. Now we have to require it.

- **Nothing obliges a device to receive one.** Not a standard, not a program, not a procurement.
- **The limit must be on the connection, not the device.** Today's programs cap the appliances you enrolled, which leaves the transformer exposed to everything else in the house.

<div class="band">

**No certification program tests whether a device can receive a limit.**

</div>

---

<!-- _class: dense2 -->

<style scoped>
thead { display: none; }
</style>

### OF 376 PRODUCTS REGISTERED UNDER THE EU CODE OF CONDUCT

## About 7% built it into the appliance

- The **EU Code of Conduct on interoperability of energy smart appliances** declares the communication layer out of scope.
- The Commission's own evaluation counted **376 registered compliant products**.

| | |
| --- | --- |
| A vendor proprietary protocol to their own cloud | 92.57% |
| **Built into the appliance** | **6.90%** |
| Dongle | 0.53% |

<div class="cap">

These are the Commission's own numbers, about its own rule. **Require an open protocol on the appliance itself. Tunnel it back to your own cloud as well if you want to, but the cloud cannot be the thing that satisfies the requirement.** Matter is local by construction, which is what makes tomorrow's session worth your attention.

</div>

---

<!-- _class: dense -->

### A CURRENT EVSE CERTIFICATION PROGRAM, SCORED AGAINST SIX TESTS

## It certifies dispatch, and neither signal

| Test | Verdict | In the released specification |
| --- | --- | --- |
| **1. An objective, not operation** | <span class="copper">**Not met**</span> | A Charging Schedule Function with default and **dispatch** schedules |
| **2. Open all the way to the appliance** | <span class="green">**Met**</span> | Mapped onto an open protocol that terminates on the charger |
| **3. A server the customer chooses** | <span class="copper">**Not met**</span> | "server address" and "endpoint": zero occurrences |
| **4. Direct from the utility** | <span class="copper">**Not met**</span> | Aggregator mediated throughout |
| **5. A limit that holds locally** | <span class="copper">**Not met**</span> | "capacity limit", "import limit", "export limit": zero occurrences |
| **6. The customer who cannot respond** | <span class="green">**Met**</span> | A local override, which expires every time the vehicle is unplugged |

---

## Yes, and also capacity

- **Everything you will hear tomorrow is right, and none of it is enough on its own.** Matter makes the home coherent and does it locally: one commissioning experience across vendors, a price cluster already in the specification, and no cloud in the middle. OpenADR carries the grid's need to the customer's own equipment. Open source removes the cost of implementing both.
- **The price half is converging.** Four of the standards in this room carry a price today, and one of them is serving real prices to anybody who asks, right now, with no account.
- **The capacity half is defined in several specifications, required by none, certified by none, and absent from the marks.**

<div class="band">

**This is not a gap in anyone's design. It is a gap in what we ask for.**

</div>

---

<!-- _class: dense2 tight -->

### ONE ASK

## When you write a program, a tariff or a procurement, ask for both

- **Ask for a price the device can read**, from a server the customer can point somewhere else.
- **Ask for a connection limit the device must respect**, that holds when the network is down.
- **Then certify that it does.** A mark that certifies dispatch and neither signal tells a buyer nothing about whether the grid can be protected.

<div class="cta">

<span class="lbl">The ask</span>

**Nobody in this room has to invent anything to do this.** Both signals are already defined in the standards you already build on. **Put them in the next requirement you write, and the market will deliver them inside two years.**

</div>

---

<!-- _class: dense2 -->

### FOR YOUR TABLES

## Four questions I would like your answers to

- **What is the biggest blocker:** the specification, the obligation, or the business model?
- **Who should own the connection limit?** The DNO publishes it, the customer lives under it, the device obeys it, and today no one carries it between them.
- **What evidence would unlock investment?** Name the specific proof your organization would need.
- **If a limit arrived at the house tomorrow, what in your product would act on it?**

<div class="band">

I am here for both days. **Come and tell me I am wrong.**

</div>

---

<!-- _class: alt -->

### EVERYTHING HERE IS PUBLIC AND FREE

## Where to find all of this

| | |
| --- | --- |
| **The price server** | `price.grid-coordination.energy/openadr3/3.1.0/programs?limit=5` |
| **User guide, tutorials, client libraries** | `github.com/grid-coordination` |
| **The argument, in full** | `grid-coordination.energy` |
| **The six tests** | `grid-coordination.energy/presentations/` |

<div class="cap">

No account, no contract, no enrollment on any of it.

</div>
