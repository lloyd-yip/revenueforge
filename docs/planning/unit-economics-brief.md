# RevenueForge — Unit Economics & Capacity Model — SOURCE BRIEF

> **Status:** Requirements LOCKED from Lloyd's voice notes (session 2026-08-19). Build NOT yet greenlit — clarifying questions outstanding.
> **Purpose of this file:** compaction-proof capture of everything Lloyd specified. This is the source of truth for the model. Do not rebuild requirements from memory — read this.
> **Deliverable:** an interactive, spreadsheet-like financial model (HTML) with editable assumptions and live recalculation.
> **Related docs (same folder):** `revenueforge_briefing.md` (offer/ICP/positioning) · `webinar_reference.md` (paid-audit model, locked 2026-08-12) · `webinar_sections_5-6_draft.md` (CTA copy) · `brain_refactor_roadmap.json` (X4 = paid audit front door)

---

## 0. THE TASK, IN ONE PARAGRAPH

Model RevenueForge's unit economics end-to-end — from webinar invites through to closed high-ticket deals — in order to (a) decide how much demand to generate now, (b) find the delivery capacity ceiling, (c) determine when to hire and for which role, and (d) establish what RevenueForge can afford to pay for talent. The model must be **interactive and assumption-driven**, because almost every conversion rate in it is currently unknown.

**Lloyd's framing:** "This might be putting the cart before the horse, but we have an acquisition engine that we know works." The engine is proven; everything downstream of it is not.

---

## 1. THE FUNNEL — STAGE BY STAGE

```
INVITES  →  QUALITY ATTENDEES  →  PAID AUDITS ($897)  →  CLOSED DEALS ($29K+ LTV)
   ↑              ↑                      ↑                        ↑
 uncapped     10min+ stay          the pay gate            delivery-constrained
```

### Stage 1 — Invites → Quality Attendees

| Item | Value |
|---|---|
| **Invite supply** | Effectively **uncapped**. QS infrastructure gives a hypothetically infinite lead pool. The only decision is invites *per week / per event*. |
| **"Quality attendee" definition** | Showed up live **AND stayed ≥10 minutes** (30 min as an alternate threshold). **1-minute bouncers count as zero.** |
| **Floor benchmark (QS actual, most recent webinar)** | **250,000 invites → ~250 quality concurrent attendees** |
| **Ceiling benchmark (best QS clients)** | **~30,000 invites → a few hundred attendees** — an order-of-magnitude (≈10×) better efficiency |
| **MODELING DECISION (locked)** | **Floor = QS's rate. Ceiling = 5× QS efficiency.** |
| **Rationale for the floor** | RF's offer is *at least* as compelling as QS's. If the reason other clients out-convert QS is a sexier offer, RF's offer is also sexier than QS's — so RF should never underperform QS's floor. |
| **Demonstrated capability** | Could reliably drive **250–350 live concurrent attendees per event**, every event, if pushed. |

### Stage 2 — Quality Attendees → Paid Audits

**QS observed data (NOTE: QS's CTA is a *free* call — not directly transferable):**

| Event | Concurrent quality attendees | Calls booked | Rate |
|---|---|---|---|
| Most recent | 250 | 25 | 10% |
| Another | 280 | 50 | ≈18% |

- **Working QS range: 10–20%** attendee→call, webinar-only
- **Email follow-up / automation adds ~10–15% more total conversion** on top of the live webinar number. *(Ambiguity flagged: relative lift vs. absolute percentage points — reads as relative.)*

**Why RF's rate will differ — adjustments to apply:**

*Pushing the rate UP:*
- RF's offer is materially **sexier and more differentiated** than QS's
- **AI offers are hot right now** (qualitative — Lloyd's industry conversations)
- **Money-back guarantee is deliberately loose**: subjective "didn't see value" → refund on request
- **Targeting ≥$2.5M recurring run-rate**; to that buyer $897 should read as **trivial** — *conditional on targeting being accurate*

*Pushing the rate DOWN:*
- It is **paid at all**. Cash up front, one-time payment. That is real friction the guarantee softens but does not remove.

**Lloyd's estimate:** *"almost certainly below 10%, although I'm very willing and hopeful that I'm wrong."*
**Scenarios he named: 3% / 5% / 7% / 10%.**

### Stage 3 — Paid Audits → Closed High-Ticket Deals

- Audit buyer is **warm, cash-committed, and you get a long high-value session** to build the case
- Lloyd: *"It would be crazy if we were to close 25% of them, 50% of them even. I don't think it would be crazy at all."*
- **Model close rate as a wide range: 25% / 35% / 50%** (with lower scenarios available)
- **Key derived metric wanted: how many audits are needed to close one deal**

---

## 2. PRICING & LTV

### The audit (front door)
- **$897**, one-time, paid up front
- **Guarantee:** subjective — if they don't see value they can request a refund
- **Function #1: self-liquidates marketing spend.** Makes it worth Lloyd's time to take the call.
- **Function #2: it is a QUALIFICATION GATE, not just revenue.** It prevents high-volume free bookings flooding the calendar. Lloyd: until sales reps are hired, he *does not want* high call volume — fewer calls at materially higher lead quality is the better outcome.

### The high-ticket offer (pricing NOT final)
- **$20K+ upfront** → covers a **3-month implementation period**
- Then **recurring ~$3–4K/month** (undecided)
- **Annual lock-in → discount**, in exchange for more cash collected upfront

### Conservative LTV baseline (use as the model default)
```
$20,000 upfront            (covers months 1–3)
+ $3,000/mo × 3 months     (months 4–6)
= $29,000 LTV @ 6-month retention
```
**This is explicitly a FLOOR, not a forecast.** Lloyd: *"I think it could be higher than this but for simplicity's sake maybe that's just what we lock it in at."* Real retention could be years; price per month could rise as value is demonstrated. **The model must let LTV, retention, and monthly price flex upward.**

### Marketing cost
- **Near-term = unusually low.** The QS acquisition infrastructure is already built and paid for — a sunk cost being reused. RF does not need significant new marketing expenditure right now.
- ⚠️ **Treat this as a PHASE-1 ADVANTAGE, not a permanent condition.** The model should be able to switch it on and off.

---

## 3. THE BINDING CONSTRAINT — DELIVERY

**This is the central insight of the entire brief.**

> "If there was no limit to capacity we'd be fucking rolling in cash — but that's not the case. The limitation is going to be delivery."

- **Demand generation is NOT the bottleneck.** It's genuinely scalable and could feed an entire sales team.
- **Lloyd's own call capacity is NOT the biggest bottleneck** either (he said so explicitly).
- **Delivery capacity IS the bottleneck.**

**Why delivery time is unknown:**
- Internal dogfooded infrastructure ≠ deployable for an external company
- Unknown: surprise challenges, real timelines, friction of working with an external team, how much customization each client demands

### → The model must run BACKWARD, not forward

```
delivery capacity (clients/month)
    → deals needed
        → audits needed
            → quality attendees needed
                → invites needed
```

### Month-1 posture: HARD MAX = 1 CLIENT
- Not multiple. Hyper-conservative on purpose.
- Want the **ideal** client — ideal on ICP **and** ideal on the use cases they're asking for
- Purpose: make it the **textbook reference engagement**, producing:
  - SOPs
  - automations that make future client launches easier
  - a real expected launch timeline
  - an energy-required baseline
- Reasoning: onboarding several at once = risk, and Lloyd wants to genuinely do right by the people investing in RF

---

## 4. RESOLVED TENSION — SUPPLY vs. DEMAND THROTTLING

**Two philosophies were weighed:**

*A — Throttle invites* so you never book audits you can't service. Avoids telling people "you'll have to wait." Counter-benefit: a waitlist could create scarcity ("these guys are hot shit").
→ Lloyd: **"I'm not convinced it is the best play."**

*B — Over-supply invites* (LLOYD'S LEAN):
- Compensates for conversion rates that may come in lower than expected across the board → hit results earlier
- Accept booking more audits than can be implemented; some sit on hold
- Waitlist may read as scarcity/status anyway — psychological upside
- Collects more cash up front → validation
- **Strongest reason: faster statistical significance on the funnel.** Confident unit economics sooner → easier decision-making later

**AND it is a low-stakes, reversible decision:** too few → next webinar sends more; too many → send less, or skip a webinar entirely. Not worth agonizing over.

---

## 5. HIRING SEQUENCE (deliberate order)

1. **NOT sales first.** Sales is most efficient with Lloyd closing — better close rates, and no commission paid on his own closes.
2. **Delivery first — but do not hire immediately.** Geri first raises his *own* leverage: improve processes and operations using **Claude Code skills + agents** so he can do more solo.
3. **Only then bring in a human** — into an already-optimized delivery process, so the first hire lands on maximum leverage rather than into chaos. Lloyd: this "increases the margin of failure each servicing up to its utmost."
4. **Then add developers**, train them → model needs **marginal capacity per developer** and **marginal revenue/margin per delivery hire**.
5. **Sales hires later.** Lloyd would take a handful of audits/week, but he has other commitments. **He will inevitably be pulled into delivery anyway** — the sales/marketing brain and high-level architecture strategy is him. Geri owns technical delivery; program strategy is Lloyd.
6. **End state:** delegate sales too → Lloyd becomes CEO.

### Energy constraint (a real model input, not a footnote)
Margin per unit of time is **unambiguously healthy** — that is *not* the question. The constraint is **available time and energy**: QS is still being built, plus social lives, finite energy. The model needs an explicit assumption for **max clients/month at zero hires**.

---

## 6. WHAT THE MODEL MUST OUTPUT

1. The **delivery constraint** — clients/month servable, at each staffing level
2. **Revenue + profitability ceiling under a no-hire scenario**
3. **When to hire** — a metric-based trigger, computed *in advance*
4. **How the revenue ceiling AND the profit margin move with each hire added**
5. **How many audits are needed to close one deal** (and therefore how many attendees, and therefore how many invites)
6. **Cost of delivery, CAC, and LTV** — because these three together determine payroll allocation

---

## 7. THE DELIVERABLE — INTERACTIVE HTML MODEL

Lloyd's words: *"create some sort of HTML document where it's almost a good spreadsheet… things that can control for assumptions and toggling aggressive assumptions versus conservative assumptions… I can also just modify it directly in the thing itself across everything… it behaves like an Excel spreadsheet where the math changes."*

**Requirements:**
- Behaves like a **live spreadsheet** — change an input, everything downstream recalculates immediately
- **Preset scenario toggles: conservative / base / aggressive**
- **Every assumption directly editable in the UI** — not just the presets. Conversion rates at every stage, pricing, retention, capacity, salaries, everything.
- **Pre-loaded with the defaults captured in this brief**

### The four stated purposes — these ARE the acceptance criteria
1. **Motivation.** Lloyd, verbatim: *"Part of this is because I just want to see the numbers and have them hopefully be awesome and drive me to work harder and give me the motivation because I see the upside is fucking huge."* The upside case must be visible and legible, not buried.
2. **Load-balance the funnel now** — what invite volume to feed in this month.
3. **Hiring trigger, in advance.** *"The best time to hire is before you kind of need them, because if you're doing it right, as the pain becomes really really huge, then you're already almost too late."* Needs a forward-looking metric signal, not a pain-based one.
4. **Payroll allocation.** Knowing cost-of-delivery + CAC + LTV tells Lloyd what this talent is actually worth. He explicitly has **not** settled what a dev or a salesperson is worth to RF, or what he can afford to pay.

---

## 8. OPEN QUESTIONS / FLAGS (unresolved at time of writing)

- **ICP floor conflict:** these notes say targeting **≥$2.5M** run-rate. The locked briefing says **$3M hard floor / $5–20M core / $25M soft ceiling**. Which governs the model?
- **Follow-up lift ambiguity:** is "+10–15% from email follow-ups" a *relative* lift on total conversion or *absolute* percentage points? (Reads relative.)
- **Recurring price:** $3K or $4K/mo — undecided. Annual-lockin discount size undecided.
- **Retention:** 6 months is a deliberate conservative placeholder. Real number unknown.
- **Audit delegation:** the brain roadmap flags an unresolved question — at $897 with Lloyd personally running deep-dives, the audit doesn't scale and re-inserts Lloyd as the bottleneck. Accept it must be delegatable from day one, or run them himself while volume is low? **STILL NOT RULED.**
- **Every conversion rate in the funnel is an estimate.** Lloyd is explicitly fine with this: *"I know that there are so many assumptions built into this… but that's kind of what we need."*

---

## 9. PROVENANCE

Captured from six voice notes, session 2026-08-19. Nothing in this document is inferred beyond what Lloyd said; where a number is an assumption rather than an observation, it is labelled as such. Observed QS data (250k→250→25, 280→50) is real; everything downstream of the paid-audit gate is estimate.

---

## 10. SHIPPED — PHASE 1 (2026-08-19)

**Live:** https://claude.ai/code/artifact/a64bd1bd-6993-4e30-9e59-412c7c90c73d
**Source:** `unit_economics_model.html` (this folder)

**Scope of phase 1: Lloyd + Geri only, no hires.** The hiring extension is the next build.

### Model structure as shipped
Reads top-down in causal order: **capacity → target → funnel**.

- **Capacity is not constant.** Hours available are fixed; what improves is *hours per client*. `efficiency(m)` slides from 1.0 to the floor over `monthsToFloor`, scaling both onboarding and upkeep hours.
- **Baseline = 100 hrs to onboard one client** (70 technical + 30 human contact), derived line-by-line, not guessed.
- **Efficiency floor = 40%** (40 hrs: 20 technical + 20 meetings). The floor is the *human-contact residue* — technical work compresses ~3.5x, meetings ~1.5x. Breaking below it requires changing delivery format (group onboarding, recorded training), not better code.
- **One-time platform build = 80 hrs**, modelled separately. Making single-tenant dogfooded apps multi-tenant. Lands entirely on client #1, never repeats, must not hide in a per-client average.
- **Billing window ≠ build time.** The $20k covers a 3-month billing window; recurring starts after it. Actual build time is separate and is what consumes capacity. Beating the window is free capacity.
- **Acquisition is throttled by QUEUE DEPTH, not free hours** — at equilibrium free hours are ~0 by definition, so a free-hours trigger would kill selling permanently. Pauses when closed-but-unstarted deals exceed `qThresh` months of onboarding capacity, or when there's no room to start anyone.

### Headline outputs (conservative preset)
| | |
|---|---|
| Starts/month today | 1.18 |
| Two-person ceiling | 2.94 (~14 live clients) |
| Cash @ month 12 | ~$87k/mo |
| Cumulative cash, 12 months | ~$605k |
| Audits/week @ ceiling | ~2.7 vs Lloyd's limit of 5 |

**Key finding: delivery is the constraint for the entire first year.** Lloyd's calendar has large headroom throughout. A commission-only rep needs 5.0 deals/month ($2k/deal at 10% of upfront) — 1.7x beyond the two-person ceiling. **Hire delivery before sales.**

### Answers locked during the build
- Profit split **60/40 Lloyd**; commission **10% of upfront only**
- Lloyd's audit ceiling **5/week** absolute max (prefers 3)
- Rep: no base, 10% commission, ~8 audits/week ceiling, discounted close rate, 50% calendar for first 3 months
- Expansion revenue **off**; annual-prepay discount **not modelled**; ramp-to-productive **removed** (absorbed into a conservative hire-efficiency figure)

### Open / next
1. **Hiring extension** — the phase-2 build Lloyd asked for.
2. **Verify the 80-hour platform estimate with Geri** — least-informed number on the page, and it costs the whole first month.
3. Efficiency currently improves with *time*; improving with *clients completed* would be truer (you learn by delivering).
4. No lever yet for clients on non-standard CRM stacks (2-3x cost). Probably a qualification rule, not a lever.

---

## 11. SESSION 2 — WHAT THE MODEL BECAME (2026-08-20)

**Live:** https://lloyd-yip.github.io/revenueforge-model/ · **Repo:** lloyd-yip/revenueforge-model (public, GitHub Pages)
**Local clone:** `~/projects/revenueforge-model` · deploy with `./deploy.sh "message"` (stamps the build, copies to Desktop, pushes)

### Structure: four tabs, one engine
One simulation runs the whole arc; each tab is a window onto a phase, and the boundaries are COMPUTED, not fixed.

1. **Startup** — you + Geri. Ends when capacity is full AND efficiency has floored.
2. **Scale delivery** — delivery hires. Ends when your calendar becomes the constraint.
3. **Scale diagnosis** — diagnosticians (NOT sales reps). Ends when the system re-stabilises.
4. **Full arc** — everything on one axis.
5. **Ideas** — 7 open questions the model surfaces but does not answer.

### The four findings that changed the business, not just the model

**1. The audit IS the architecture.** It closes the deal, diagnoses, and produces the build spec in one paid session.
Therefore a commission-only closer CANNOT do it, and sales reps were removed from the model entirely. The scaling
path is diagnosticians / AI technical architects. It also means the audit pre-pays part of the build — hence the
"architecture the audit covers" lever.

**2. Pricing beat optimisation, decisively.** Phase-based pricing ($20k/$3k → $30k/$5k → $40k/$7k) roughly DOUBLED
cash and MRR on identical delivery. That outperformed every capacity lever combined. The business was underpriced,
not under-optimised. Price is locked at signing; new pricing applies only to new clients.

**3. Retention has to be staffed.** The model previously assumed retention for free. Now a client-success hire
lands per 25 active clients at $6k/mo — no delivery hours, no deals, pure payroll — so the retention assumption
carries a cost. Charging $7k/mo for ~5 hrs of attention is the main churn risk the model still cannot see.

**4. Three constraints, in strict order.** Delivery capacity → your calendar (5 audits/wk) → invite volume
(~1.5M/mo, the sane ceiling). Past the invite ceiling only CONVERSION helps, because volume is fixed. The funnel
panel names which one is currently binding.

### Where it lands (conservative preset, ~31 months)
| | |
|---|---|
| Cash / month | ~$432k |
| MRR | ~$140k (31% of cash) |
| Net / month | ~$359k |
| Active clients | 40 |
| People hired | 7 |
| Diagnostician comp | ~$27k/mo (~$322k/yr) at $8k base + 10% upfront + 5% recurring (12 mo cap) |

Annualised ≈ **$5.2M revenue**, realistic EBITDA ≈ **$3.1M (~60%)** after founder comp, real marketing, G&A and
honest delivery salaries. That crosses PE platform scale (~$3M EBITDA), up from bolt-on territory.

**Indicative valuation:** $12–19M as-is (4–6×, project-heavy). $22–28M if recurring becomes the majority (7–9×).

### The two numbers everything rests on — both unverified
1. **Onboarding hours at maturity (~34 hrs).** If it is really 60, headcount doubles and margin collapses toward
   normal-agency levels. Measure it on clients #1 and #2.
2. **Upkeep hours per live client (~5/mo).** Sets the capacity ceiling AND the parity price for recurring.

### Still not modelled, deliberately
CAC (marketing sits at $0 because QS infrastructure is currently free — the biggest hole), expansion revenue,
referrals, churn as an output rather than an input, and the diagnosis library that would make the diagnostician
hire safe.
