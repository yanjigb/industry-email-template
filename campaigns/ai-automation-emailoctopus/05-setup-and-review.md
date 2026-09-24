# 05 — EmailOctopus Setup Checklist + Copy Review Summary

## A. Setup checklist

### A1. Account structure

- [ ] Custom fields created (02 §1): `audience`, `use_case`, `personal_note`, `proof_point`, `company`, `role` (plus standard `first_name`)
- [ ] Tags created (02 §2): four `emo_*`, `arc_active`, `arc_done`, `arc_won`, `segment_unknown`, `fit_high`
- [ ] Segments created: `aud_smb`, `aud_marketing`, `aud_agency`, `aud_enterprise`, `aud_unknown`, `1to1_ready`, discovery
- [ ] Placeholder `[AUDIT_LINK]` replaced with real booking URL everywhere
- [ ] Brand name confirmed in copy (SignalOS assumed — see 01)

### A2. List migration

- [ ] Export full list
- [ ] Enrichment pass (02 §3 rules): every row has `audience` + one `emo_*` **or** `unknown` → discovery
- [ ] `fit_high` + `personal_note` filled for top 5–10% only
- [ ] `proof_point` filled per audience (real numbers from 01)
- [ ] Re-import (update by email, no duplicates)
- [ ] Hard bounces + non-consent suppressed
- [ ] Spot-check **10 contacts**: fields + tags complete

### A3. Automation / sequence build

- [ ] Discovery branch live for `aud_unknown` (D1–D2)
- [ ] Arc entry gate: `audience` ≠ unknown AND one `emo_*` AND NOT `fit_high`
- [ ] E1 subject + opener variants wired by `emo_*` (4 paths or 4 parallel sequences merging at E3)
- [ ] E3 body branch by `audience` (4 variants)
- [ ] E4 agitation paragraph by `emo_*`
- [ ] E5 `{{proof_point}}` renders per audience
- [ ] Goal: click on `[AUDIT_LINK]` → tag `arc_won` + exit
- [ ] `fit_high` skips E1–E2 (enters at E3) **or** excluded from arc (option A from 04)
- [ ] Timezone / send window set (business hours; stagger over 2 weeks)

### A4. Seed / render matrix (before live)

- [ ] Minimum: **4 audiences × 4 emotions** = 16 test renders (or 4 audiences if only openers vary and you test one emotion each + all 4 openers separately)
- [ ] Merge fields resolve: no empty `Hello ,` / `{{use_case}}` blanks — empty `use_case` falls back to generic line (edit E3 if needed)
- [ ] `personal_note` renders for a `fit_high` seed
- [ ] Mobile preview: subject truncation acceptable
- [ ] From-name, reply-to, unsubscribe, physical address OK for deliverability

### A5. Verification (from plan)

| # | Check | Pass criteria |
|---|---|---|
| 1 | Field integrity | 10/10 sampled contacts have audience + one emo tag |
| 2 | Render matrix | All seeds resolve merge tags |
| 3 | Arc logic | `emo_skeptical` vs `emo_urgent` → different E1, same E3–E6; click exits |
| 4 | 1:1 swap test | 3 samples fail "send to another company" (i.e. are unique) |
| 5 | Quality gate | Section B below all green |
| 6 | Pilot | E1 to 10% per audience; deliverability + reply tone OK → full send |

---

## B. Copy review summary

### Pass

| Check | Result |
|---|---|
| 5-second test E1 subject + opener | Pass — pain named without pitch |
| One specific CTA per email | Pass — "Book a 20-minute automation audit" only |
| No hard-banned hype words | Pass — no game-changing / revolutionary / world-class / "in today's landscape" |
| Subject ↔ body match (no bait-and-switch) | Pass E1–E6 |
| Same voice across 4 audiences | Pass — vocabulary map only |
| No verbatim reuse across channels | Pass — email-only deliverable |
| Emotion = hook only, arc structure shared | Pass |
| 1:1 swap test (3 samples) | Pass |

### Flagged issues (fix before pilot)

1. **Proof points empty** — `{{proof_point}}` and E5 are blocked until four real case lines exist (01 §5).
2. **`{{use_case}}` empty risk** — contacts without enrichment will show blank or odd lines in E3; add fallback copy or enforce enrichment before entry.
3. **30-day claim** — used in E1/E5/E6 and samples; confirm true for standard scope or rewrite to your real SLA.
4. **Brand name** — "SignalOS" assumed from repo name; replace if trading name differs.
5. **E6 "later" reply mechanism** — confirm team will handle reply-based 90-day pause (or replace with a one-click preference link).

### Open questions (owner: you)

1. Confirm brand name + CTA URL.
2. Confirm 30-day (or actual) first-workflow timeline.
3. Supply 4 proof points (smb, marketing, agency, enterprise).
4. Choose 1:1 cadence **A** (recommended), B, or C (04).
5. Any regulated claims (SOC 2, insurance, etc.) — include only if true.

### Not included (out of scope)

- Landing page, social, ads, video (full-campaign extras from skill) — request if needed
- Live EmailOctopus clicks/imports — this repo does not hold list credentials; execute checklist in the ESP UI or via their API with your key
- Actual enrichment run on your CSV (needs export from EmailOctopus)

---

## C. Execution order (remaining)

1. [ ] Approve **01** positioning (benefit, angle, timeline, proof sources)
2. [ ] Fill proof points + audit link in **03** / **04**
3. [ ] Run **02** migration on real export
4. [ ] Build automation per **A3**; seed matrix **A4**
5. [ ] Verification **A5** → 10% pilot E1 → full rollout
6. Weekly readout: conversion by `audience` × `emo_*` (reply, click, booked)
