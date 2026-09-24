# 06 — Free Audit Delivery Email

> **Manual use only.** Paste HTML into EmailOctopus Templates (see
> `07-free-audit-template-html.html`). **This task does not create, schedule,
> or run any campaign or automation.**

**When to send:** after a contact submits `/free-audit` (import or form API).
**Goal:** deliver the free automation audit lead magnet + one path to book a call.
**CTA:** Book a 20-minute automation audit → booking URL
**Composio (done):** list fields remapped for Starter 10-field cap (see merge table).

---

## Subject

`Your free automation audit — {{FirstName}}`

**Alternates (A/B):**
- `Automation audit for {{Company}} — inside`
- `One workflow, mapped: your free audit`

## Preview text

`What to automate first for {{Company}} — checklist inside.`

## Body

Hi {{FirstName}},

You asked for the free automation audit for **{{Company}}** — it’s below (and as a short checklist you can run with your team).

### What you get

1. **Workflow shortlist** — the paths worth automating first for **{{Audience}}**, ranked by hours burned and failure cost.
2. **Manual cost math** — hours/week × loaded cost × 48 weeks for the path you named:  
   *“{{WorkflowPain}}”*
3. **Build / don’t-build rules** — when we say no, and what “done” looks like if we say yes.

### How to use it this week

- Pick **one** recurring path (not a platform migration).
- Score it: frequency × minutes × who touches it.
- If the score is high and the path crosses two tools, that’s the first build candidate.

### Who this is for

Works the same for small teams, marketing/e-comm, agencies, and ops/IT — only the vocabulary changes (hours → pipeline → margin → governance).

### Optional next step

If you want a second pair of eyes on the shortlist, book a **20-minute automation audit**. We map one workflow live and give a clear build / don’t-build call — including if it’s not a fit.

→ Book a 20-minute automation audit: `[AUDIT_LINK]`

—  
SignalOS  
Done-for-you AI automations in the tools you already run.

---

## Merge fields (EmailOctopus field tags — live on “Audience” list)

| EO merge tag | Field tag | Label | Notes |
|---|---|---|---|
| `{{FirstName}}` | `FirstName` | First name | existing |
| `{{Company}}` | `Company` | Company | **repurposed** from `Website` (Starter plan 10-field cap) |
| `{{WorkflowPain}}` | `WorkflowPain` | Workflow pain | **repurposed** from `Address` |
| `{{Audience}}` | `Audience` | Audience | **repurposed** from `Category` |

**Starter plan:** cannot add new fields (403 max 10). Creating new fields failed; UPDATE_FIELD succeeded for the three above.

### Personalization per contact

Fill fields via Composio when you have emails:

```
EMAILOCTOPUS_UPSERT_CONTACT
list_id=9663e506-7309-11f1-8e11-8f5a4d9e10ab
fields: FirstName, Company, WorkflowPain, Audience
tags: free-audit-landing=true  (check LIST_TAGS / free tag limits first)
```

Landing form should map to the **same tags** (`Company`, `WorkflowPain`, `Audience`) — project API still sends snake_case until separately updated.

## Tags to apply on send (when you wire it later — not now)

- `free-audit-landing`
- `mag_delivered` (create tag only if plan allows)

## Quality gate

- [x] One CTA, specific
- [x] No banned hype words
- [x] Subject matches body (delivery promise kept)
- [ ] Booking URL filled in `07-...html` (`https://example.com/audit`)
- [ ] Double-opt-in copy if list requires confirmation

## Explicit non-actions

- Do **not** attach this to the E1–E6 arc without a deliberate plan.
- Do **not** schedule a campaign as part of this work.
- No campaign create tool exists in Composio EmailOctopus toolkit.

## Related artifact

- Paste-ready HTML: `07-free-audit-template-html.html`
