# 04 — 1:1 Unique Email Layer (brief + 3 samples)

## Purpose

Top **5–10%** of the list (`fit_high`) receives a fully individualized email instead of generic E1–E2. Same voice, same CTA as the arc; only the scenario paragraph is unique.

---

## Selection

| Criterion | Weight | Notes |
|---|---|---|
| Audience fit (clear pain + budget) | 40% | enterprise + agency + marketing scale usually first |
| Engagement (opens/clicks last 90d) | 30% | proves consent and attention |
| Deal-size signal (role seniority, company size) | 30% | owner / VP+ / head of ops |

- Volume: **50–100 contacts** for first wave.
- Manual tag: `fit_high` + non-empty `personal_note`.

## Generation inputs (per contact)

1. `first_name`, `company`, `role`
2. `audience`
3. `use_case` (or inferred from site/role)
4. **One observed trigger** (pick exactly one):
   - job post (automation / RevOps / AI engineer)
   - tech stack visible (HubSpot + Shopify, NetSuite, etc.)
   - content they clicked / lead magnet they took
   - public event (funding, launch, expansion)

## Structure (fixed)

```
Subject: [specific to company/trigger — not generic]
Preview: one line of the unique scenario

Opener (emotion-aligned, 1 sentence — optional, may skip for 1:1)

UNIQUE PARAGRAPH (3–5 sentences) — must fail the swap test:
  "{Company} + {trigger} + {use_case} + why this path for {role}"

Bridge (shared with arc voice): what we build / ownership / 30-day path

Proof: {{proof_point}}

CTA: Book a 20-minute automation audit → [AUDIT_LINK]
```

## Swap test (quality gate)

Read the unique paragraph alone. If it could be pasted into another company's email with only the name changed → **rewrite**. Must reference: the trigger, the specific workflow, and why *this role* cares.

## Cadence (pick one — recommend A)

| Option | Flow |
|---|---|
| **A (recommended)** | 1:1 replaces E1–E2 → contact enters arc at E3 (shared education onward) |
| B | Fully separate: 1:1 only, no arc (pure white-glove; fewer touches) |
| C | 1:1 after E3 — not recommended (generic E1–E2 already spent) |

## Load into EmailOctopus

1. Generate unique paragraph externally (AI or human) → store in `personal_note`.
2. Import/update by email so only `personal_note` changes.
3. Send as:
   - **one campaign** with `{{personal_note}}` merge (fast), or
   - **individual sends** for top ~10 (highest personalization).
4. Suppress from E1–E2 via `fit_high` filter.

---

## Sample 1 — SMB

**Fields:** `first_name`=Linh · `company`=BrightNest Cleaning · `role`=Owner · `audience`=smb · `emo_primary`=emo_overwhelmed · `use_case`=quote follow-ups dropped between SMS and spreadsheet · trigger=job post for “office manager”

**Subject:** Lini, the office-manager hire and the quote pile  
**Preview:** BrightNest is posting for help — the workflow may be the cheaper first move

**Unique paragraph:**

Linh — BrightNest is hiring an office manager to catch quote follow-ups that currently live between your SMS thread and a spreadsheet. That's a real hire, and a real monthly cost, for work that's mostly "send, wait, nudge, log." We automate that path first: new quote → follow-up sequence → reply routed to you only when someone says yes or asks a real question. You keep the human close; the re-runs stop needing one.

**Bridge:** We build it inside the tools you already use, document it, and hand it over — first standard workflow on a ~30-day path, no new dashboard.

**Proof:** `{{proof_point}}` (smb)

**CTA:** Book a 20-minute automation audit → `[AUDIT_LINK]`

---

## Sample 2 — Marketing / e-com

**Fields:** `first_name`=Marcus · `company`=Northline Supply · `role`=Head of Growth · `audience`=marketing · `emo_primary`=emo_urgent · `use_case`=inbound demo leads wait overnight for routing · trigger=clicked “lead response time” article

**Subject:** Northline’s overnight demo leads  
**Preview:** The piece you opened — applied to the gap before first reply

**Unique paragraph:**

Marcus — you opened our note on lead response time; for Northline that gap is real: demo requests land overnight, routing waits on whoever is first in at 9am, and by then the buyer has booked someone else. The automation we'd build first is narrow: form → enrich → assign by segment → first reply with a real slot before your team logs on. Humans take the meetings; the queue stops depending on morning coffee.

**Bridge:** Built in your CRM/stack you already run, tested on live leads, handed to your team with docs. Standard first workflow: ~30-day path.

**Proof:** `{{proof_point}}` (marketing)

**CTA:** Book a 20-minute automation audit → `[AUDIT_LINK]`

---

## Sample 3 — Enterprise ops

**Fields:** `first_name`=Priya · `company`=Halcyon Logistics · `role`=Director of Operations · `audience`=enterprise · `emo_primary`=emo_skeptical · `use_case`=exception handling between WMS and finance re-keyed in Excel · trigger=public case: warehouse expansion in Ohio

**Subject:** Halcyon’s Ohio expansion — exceptions before headcount  
**Preview:** Scaling nodes without scaling the Excel bridge

**Unique paragraph:**

Priya — with Halcyon adding the Ohio node, the exception path between WMS and finance is about to get heavier: every mismatch still lands in Excel for someone to reconcile by hand. That's a headcount conversation hiding inside a data problem. We scope a governed automation that validates exceptions against your rules, routes only true edge cases, and writes a full audit log your security review can read — in the systems you already run, not a shadow tool.

**Bridge:** Fixed scope, your ownership, documentation and cutover review with your team. First standard automation: ~30-day path after audit.

**Proof:** `{{proof_point}}` (enterprise)

**CTA:** Book a 20-minute automation audit → `[AUDIT_LINK]`

---

## Sample QA

| Sample | Swap test | Audience language | Single CTA | No hype words |
|---|---|---|---|---|
| 1 SMB | Pass — hire + SMS/spreadsheet specific | hours, cost | ✓ | ✓ |
| 2 Marketing | Pass — overnight routing + article trigger | leads, response time | ✓ | ✓ |
| 3 Enterprise | Pass — Ohio node + WMS/finance + audit log | governance, audit | ✓ | ✓ |
