# 02 — EmailOctopus Segmentation Spec

## 1. Custom fields

| Field key | Type | Allowed values / format | Required |
|---|---|---|---|
| `first_name` | text | — | yes |
| `company` | text | — | recommended |
| `role` | text | — | recommended |
| `audience` | text (enum) | `smb` \| `marketing` \| `agency` \| `enterprise` \| `unknown` | yes |
| `use_case` | text | one line: pain + automation opportunity | for E3 / 1:1 |
| `personal_note` | text | unique paragraph for 1:1 layer; empty for bulk | 1:1 only |
| `proof_point` | text | audience-specific result sentence | for E5 |

## 2. Tags (emotion — single primary per contact)

| Tag | Meaning | Default if unknown |
|---|---|---|
| `emo_overwhelmed` | Drowning in tasks, no time | — |
| `emo_skeptical` | Tried tools/AI, burned | — |
| `emo_curious` | Watching AI, not acting | → use if opened/clicked AI content |
| `emo_urgent` | Deadline / scaling now | — |
| `arc_active` | Currently in 6-email sequence | added on entry |
| `arc_done` | Completed sequence without exit goal | added on finish |
| `arc_won` | Clicked CTA / booked (exit goal) | added on goal |
| `segment_unknown` | No audience assigned | catch-all until enriched |

**Rule:** exactly one `emo_*` tag + one `audience` value before entering the arc. If missing → discovery branch (see §4).

## 3. CSV columns for enrichment export → re-import

```
email, first_name, last_name, company, role,
audience, use_case, proof_point, personal_note,
emo_primary, source, last_engagement_date, notes
```

### Enrichment rules (one-time pass, external)

| Signal | → `audience` | → `emo_primary` |
|---|---|---|
| Role/title contains owner/CEO/founder (company &lt; 50) | `smb` | busy/no opens → `emo_overwhelmed` |
| Role: marketing/growth/ecom/CRM | `marketing` | clicked AI topic → `emo_curious` |
| Role: agency/freelance/studio + "agency" in company | `agency` | prior tool case study open → `emo_skeptical` |
| Role: ops/IT/CIO/platform + enterprise firm | `enterprise` | form fill / pricing visit → `emo_urgent` |
| Job post for automation/RevOps/AI lead | match role | `emo_urgent` |
| No signal | `unknown` | none → discovery branch |

## 4. Segments in EmailOctopus

Create saved segments:

1. `aud_smb`, `aud_marketing`, `aud_agency`, `aud_enterprise`, `aud_unknown`
2. Cross filters for seeds: `aud_* AND emo_*` (16 combinations for render matrix)
3. `1to1_ready`: has non-empty `personal_note` AND fit flag (manual tag `fit_high`)
4. Discovery: `segment_unknown OR missing emo tag` — receives **D-series** (below), not the arc

## 5. Discovery branch (D0 — before arc)

Short 2-email check for unsegmented contacts:

- **D1:** "Which best describes you?" → 4 reply-to or link buttons that set `audience` (use EmailOctopus link tags / landing if available; else reply-based manual tagging)
- **D2 (3 days later):** same CTA, simpler; then park in `segment_unknown` if no response (do not send arc)

## 6. Three-layer routing

```
                    ┌─ fit_high + personal_note ──► 1:1 campaign (replaces E1–E2)
Imported contact ───┼─ audience + emo set ────────► 6-email arc (emotion openers)
                    └─ missing audience/emo ──────► Discovery D1–D2 → re-tag → arc
```

| Layer | Coverage | Mechanism |
|---|---|---|
| Emotion openers + merge tags | 100% of arc contacts | Parallel openers by `emo_*`; shared body |
| Emotional arc E1–E6 | 100% of arc contacts | Automation, exits on CTA goal |
| 1:1 unique | top 5–10% (`fit_high`) | `personal_note` merge; skips E1–E2 |

## 7. Migration steps (checklist)

- [ ] Export full list from EmailOctopus
- [ ] Add CSV columns from §3; run enrichment rules §3
- [ ] Assign exactly one `emo_*` + one `audience` (or `unknown`)
- [ ] Flag top 5–10% as `fit_high` + fill `personal_note` for those only
- [ ] Fill `proof_point` per audience (from positioning doc)
- [ ] Import updated CSV (update by email; do not duplicate)
- [ ] Create tags + segments (§2, §4)
- [ ] Suppress hard bounces + non-consent
- [ ] Spot-check 10 contacts: fields + tags complete
- [ ] Seed-test before enabling automation
