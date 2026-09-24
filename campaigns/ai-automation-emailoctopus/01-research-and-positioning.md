# 01 — Research Brief & Positioning

> Status: **draft for approval** — no email copy ships until this page is signed off.
> Service: AI Automation (done-for-you) · Brand: SignalOS · Platform: EmailOctopus

---

## 1. Audience profiles (primary segment)

### A. Small business owners (`smb`)

- **JTBD:** Reclaim hours from repetitive admin (invoicing, follow-ups, scheduling, data entry) without hiring.
- **Fear:** "I can't afford a hire; every tool promises ease and then eats a weekend."
- **Current alternatives:** Manual work + VA hours; Zapier/Make pieced together at 11pm; spreadsheet duct tape.
- **Language cues:** time, cost, "doing everything myself," weekends, hire.

### B. Marketing / e-commerce teams (`marketing`)

- **JTBD:** Scale campaign ops and lead follow-up without more headcount.
- **Fear:** "Another tool that dies after week 2 — or a 'AI feature' that hallucinates into our brand."
- **Current alternatives:** Native platform automation, Zapier chains, intern-powered sequences, agency retainers.
- **Language cues:** leads, ROAS, follow-up, churn, handoffs, attribution.

### C. Agencies / freelancers (`agency`)

- **JTBD:** Productize delivery and protect margin per client (bill outcomes, not hours).
- **Fear:** "I sell hours — automation either threatens that or clients expect it free."
- **Current alternatives:** Subcontract VAs, template libraries, white-labeled no-code builds.
- **Language cues:** retainers, scope, leverage, delivery time, margin.

### D. Enterprise ops / IT (`enterprise`)

- **JTBD:** Standardize workflows with auditability, security, and integration that survives review.
- **Fear:** "Shadow IT, compliance gaps, another integration debt we own forever."
- **Current alternatives:** RPA vendors, in-house scripts, platform-native workflow builders, consultants.
- **Language cues:** workflow, governance, SOC 2, ROI, integration debt, change management.

---

## 2. Competitive map (3 alternatives)

| Alternative | What they sell | Messaging weakness to exploit |
|---|---|---|
| **DIY no-code (Zapier / Make / n8n)** | Tools + tutorials | Customer still owns the build, breakage, and maintenance. Time-to-value is *their* time. |
| **VA / freelancer hours** | Labor | Coverage is human-shaped: sick days, inconsistent quality, no compounding system. |
| **Generic AI consultants / agencies** | Decks + strategy | Strategy without a working automation in your stack. Slide-ware, then handoff. |

Adjacent: platform-native automation (HubSpot, Shopify Flow, Power Automate) — locked to one suite; cross-tool gaps stay open.

---

## 3. Key insight (campaign exploit)

> Every competitor sells **tools** or **hours**. SignalOS sells a **working automation your team owns**, live in the stack you already run — in weeks, not another dashboard to learn.

Supporting tension: prospects are not short on AI *awareness*; they are short on **one reliable workflow that runs without them babysitting it**.

---

## 4. Positioning brief

| Element | Locked statement |
|---|---|
| **Core benefit** | We build the AI automations your team keeps talking about — live in your stack in 30 days, no new hires. |
| **Positioning formula** | SignalOS helps [segment] get hours and errors out of critical workflows by building done-for-you AI automations inside the tools they already use. |
| **Campaign angle** | *"You don't need another tool to learn — you need one workflow that runs without you."* |
| **Tone profile** | Direct, specific, zero hype. Same voice for all four audiences; only vocabulary shifts (hours → margin → governance). Never hype words, never fake urgency, never hollow proof. |

### Vocabulary map (tone stays fixed, words shift)

| Audience | Lead with | Avoid |
|---|---|---|
| smb | hours back, one workflow, fixed scope | jargon, "transformation" |
| marketing | follow-up speed, handoffs, pipeline | vague "growth" |
| agency | margin, delivery days, client deliverable | "replace your team" |
| enterprise | governance, audit trail, integration scope | startup slang, emoji-heavy CTAs |

### Claims we will support (only these)

- Timeline claim: first automation live path framed as **30 days** for standard scope (adjust if your delivery differs — **open question** below).
- Ownership: client owns the workflow in their tools.
- Process: scoped audit → build → handoff with docs.

Do **not** claim: revenue lift %, "hundreds of clients," SOC 2 / compliance certifications unless true (**open questions**).

---

## 5. Approval checklist

- [ ] Core benefit sentence is accurate to how you actually deliver
- [ ] Campaign angle matches a real differentiator (not aspirational)
- [ ] 30-day timeline claim is true for your standard package
- [ ] Proof points below are real numbers you can stand behind

### Proof points to fill before E5 ships

| Audience | Proof slot (`proof_point` field) | Source |
|---|---|---|
| smb | e.g. "Cut weekly admin from 6h → 45m for [company]" | your case data |
| marketing | e.g. "Lead response time 4h → 4m, [n] demos/mo" | your case data |
| agency | e.g. "Onboarding delivery 2 weeks → 3 days per client" | your case data |
| enterprise | e.g. "Reconciled [n] invoices/mo with full audit log" | your case data |

**Open questions:** (1) confirm brand name to use in copy — SignalOS assumed; (2) confirm 30-day claim; (3) provide 4 real proof points.

**CTA destination (resolved):** lead magnet landing = `{{FRONTEND_URL}}/free-audit` (page at `apps/frontend/src/app/(marketing)/free-audit/`). Booking CTA for emails remains `[AUDIT_LINK]` (Calendly or equivalent — still fill before send).
