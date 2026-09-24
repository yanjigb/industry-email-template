# 03 — 6-Email Emotional Arc Sequence

**Service:** AI Automation (SignalOS) · **Arc:** problem → empathy → education → agitation → proof → CTA
**Merge fields used:** `{{first_name}}` `{{company}}` `{{use_case}}` `{{proof_point}}` `{{audience_label}}`
**CTA (all emails):** Book a 20-minute automation audit → `[AUDIT_LINK]`
**Rule:** Subject/preview vary by `emo_*` where marked; body shared unless noted. One CTA per email.

`{{audience_label}}` maps: `smb` → “your business” · `marketing` → “your team” · `agency` → “your agency” · `enterprise` → “your org”

---

## E1 — Day 0 · Pattern-interrupt (name the pain, no pitch)

**Emotion openers** (replace first 1–2 sentences only):

| Tag | Opening lines |
|---|---|
| `emo_overwhelmed` | `{{first_name}}` — you're not behind. Your process is still doing work a workflow should own. |
| `emo_skeptical` | `{{first_name}}` — if you've already tried Zapier chains or an "AI pilot" that died in month two, this isn't that pitch. |
| `emo_curious` | `{{first_name}}` — AI is loud right now. Most teams are still watching. One working automation beats ten bookmarked tools. |
| `emo_urgent` | `{{first_name}}` — if the deadline is real (pipeline, headcount, a process that broke this quarter), waiting on another tool evaluation burns the week you don't have. |

**Subject variants (by emotion):**

| Tag | Subject | Preview |
|---|---|---|
| `emo_overwhelmed` | The task that ate your Tuesday | Not a productivity hack — a workflow that should already exist |
| `emo_skeptical` | Not another AI tool | One automation, in your stack, that you own |
| `emo_curious` | The first workflow worth automating | Skip the hype. Start with one job that runs without you. |
| `emo_urgent` | 30 days, one workflow | Path from audit call → live automation — no new hire |

**Shared body (after opener):**

Most of what drains `{{company}}` isn't strategy. It's the same five steps someone re-runs every week: copy between tools, chase a missing field, remind a human, fix the error, start over.

We build AI automations for that layer — inside the tools you already pay for. No new dashboard for your team to learn.

Over the next two weeks I'll send four short notes: what we automate first, what it costs you to keep doing it manually, and what a real handoff looks like.

**CTA (soft, in P.S.):** P.S. Prefer to skip the notes? Book a 20-minute automation audit — we map one workflow and tell you if it's worth building. `[AUDIT_LINK]`

---

## E2 — Day 2 · Empathy (“day in the life”)

**Emotion openers:**

| Tag | Opening |
|---|---|
| `emo_overwhelmed` | If your calendar is full and the "important" work keeps sliding right, the issue usually isn't discipline. |
| `emo_skeptical` | You've been sold automation before — often as a tool license with a webinar attached. |
| `emo_curious` | Curiosity is fine. The gap is almost never ideas — it's who turns one idea into something that runs on Monday. |
| `emo_urgent` | When you're the escalation path for every exception, speed is the product. |

**Subject (shared):** What a week looks like without the re-runs  
**Preview:** Not hustle — the same five steps, every cycle

**Body:**

`{{first_name}}`, here's the pattern we see with `{{audience_label}}` before we touch anything:

- Someone exports a list, pastes it into another tool, and hopes the columns line up.
- A lead sits four hours (or four days) because the handoff lives in someone's head.
- The same invoice / ticket / brief gets re-keyed twice — once by a person, once by a spreadsheet formula that breaks quietly.
- Friday is spent reconciling what the week *said* happened.

None of that is a people problem. It's a missing system.

We don't ask `{{company}}` to "adopt AI." We pick one painful path, write the automation, run it beside your current process until it's boring, then hand you the keys.

**CTA:** If one of those lines was too accurate, book the 20-minute audit. We'll name one workflow worth fixing first. `[AUDIT_LINK]`

---

## E3 — Day 5 · Education (use-case)

**Emotion openers (short):**

| Tag | Opening |
|---|---|
| `emo_overwhelmed` | Start small. One workflow, hours back this month — not a platform migration. |
| `emo_skeptical` | Here's the actual scope of a first build — no pilot theater. |
| `emo_curious` | Concrete example, your stack: this is what "automated" means when we say it. |
| `emo_urgent` | The fastest path to results is a bounded first workflow, not a 6-month roadmap. |

**Subject:** The first workflow we'd automate at `{{company}}`  
**Preview:** Based on your world: `{{use_case}}` — or the closest match

**Body:**

`{{first_name}}` — for `{{audience_label}}`, the highest-ROI first build is usually one of these:

**If audience = smb**  
Invoice chase + follow-up: draft reminders, log replies, flag only the accounts that need a human.

**If audience = marketing**  
Lead routing + first response: enrich, score lightly, assign, and send the first reply before the lead cools.

**If audience = agency**  
Client onboarding path: intake form → project setup → kickoff assets → status ping — same steps every client, zero re-build.

**If audience = enterprise**  
Exception queue: pull exceptions from system A, validate against B, route only the edge cases to humans with a full log.

Yours, in one line: **`{{use_case}}`**  
(If that field is empty or stale, bring the real one to the audit — we'll re-rank.)

We build in your existing tools, document every step, and your team can edit it without calling us for a comma.

**CTA:** Bring `{{use_case}}` (or your version) to a 20-minute audit — leave with a build/no-build call. `[AUDIT_LINK]`

---

## E4 — Day 8 · Agitation (cost of waiting)

**Intensity by emotion** (swap the middle paragraph):

| Tag | Agitation paragraph |
|---|---|
| `emo_overwhelmed` | Every week the manual path runs, it quietly taxes the people you can least afford to tax — the ones already at capacity. |
| `emo_skeptical` | The expensive part isn't a failed tool. It's six more months of "we should automate that" while the same process burns payroll. |
| `emo_curious` | Interest compounds only when it ships. The teams that win with AI aren't the ones who watched longest — they're the ones with one workflow in production. |
| `emo_urgent` | Every sprint without the fix is a sprint where the broken path is still the official path — and people work around it harder. |

**Subject:** What the re-runs cost `{{company}}`  
**Preview:** A rough math exercise — no scare tactics, just the ledger

**Body:**

`{{first_name}}`, quick math for `{{audience_label}}`:

Take the tasks tied to **`{{use_case}}`** (or the closest recurring path).
Estimate hours/week × loaded hourly cost × 48 weeks.
Add the cost of one missed handoff — a late lead, a wrong invoice, a client who waited a day.

That number is usually larger than the build.

**Agitation line by emotion (use after the math):**

| Tag | Line |
|---|---|
| `emo_overwhelmed` | You don't need more personal discipline. You need the path to stop needing you. |
| `emo_skeptical` | If you've been burned before, the fix is a fixed scope, a working demo before full rollout, and an exit if it doesn't hold. |
| `emo_curious` | The gap between "AI-curious" and "AI-operational" is one shipped workflow — not a bigger stack. |
| `emo_urgent` | If this quarter's number depends on it, the audit is the shortest honest next step. |

**CTA:** Run the real numbers with us — 20 minutes, one workflow, clear build cost range. `[AUDIT_LINK]`

---

## E5 — Day 11 · Solution + proof

**Emotion openers:**

| Tag | Opening |
|---|---|
| `emo_overwhelmed` | You don't have to run this project. That's the point. |
| `emo_skeptical` | Scope, timeline, and ownership — the three things usually missing from AI pitches. |
| `emo_curious` | What "done" looks like, concretely. |
| `emo_urgent` | From audit call to first live workflow: the path below. |

**Subject:** How the build actually runs  
**Preview:** Scope → build → handoff. `{{proof_point}}`

**Body:**

`{{first_name}}` — three steps, no theater:

1. **Audit (20 min)** — pick one workflow; decide build / don't build.
2. **Build (scoped, ~30 days for standard first automation)** — we implement in your tools, test against real data, you review before cutover.
3. **Handoff** — documentation, owner on your side, edit path that doesn't require us.

**Proof for `{{audience_label}}`:** `{{proof_point}}`

You own the automation. We don't hold your process hostage in a retainer you can't leave.

**CTA:** Book the audit — if it's not a fit, we'll say so in the call. `[AUDIT_LINK]`

---

## E6 — Day 14 · Soft urgency + CTA

**Emotion openers:**

| Tag | Opening |
|---|---|
| `emo_overwhelmed` | No pressure pitch — just a clear door. |
| `emo_skeptical` | Final note from this sequence. Either the audit is useful or it isn't; you'll know in 20 minutes. |
| `emo_curious` | Last email in this series. The next step is one call, not a course. |
| `emo_urgent` | If you need this live this quarter, the audit this week is what keeps the 30-day path real. |

**Subject:** Last note — one workflow, 20 minutes  
**Preview:** Audit link stays below; series ends after this

**Body:**

`{{first_name}}`, that's the sequence.

If `{{use_case}}` (or the path behind it) is still running on humans re-typing and re-checking, the audit is the fastest way to get a yes/no on automating it.

**If you book this week:** we'll run the mapping session against your real process — not a generic demo.

`{{proof_point}}`

**Hard CTA block:**

→ Book a 20-minute automation audit: `[AUDIT_LINK]`

If now isn't the time, reply with one word — **later** — and we'll pause outreach for 90 days.

---

## Sequence logic (automation)

| Step | Condition | Action |
|---|---|---|
| Entry | Has `audience` ≠ unknown AND one `emo_*` AND not `fit_high` | Tag `arc_active`; send E1 (emotion subject/openers) |
| +2d | Not goal | E2 |
| +5d | Not goal | E3 (audience body branch) |
| +8d | Not goal | E4 |
| +11d | Not goal | E5 |
| +14d | Not goal | E6 → tag `arc_done` |
| Any time | Clicks `[AUDIT_LINK]` or goal event | Tag `arc_won`, remove `arc_active`, exit sequence |
| `fit_high` | Has `personal_note` | Skip E1–E2; enter at E3 **or** fully separate (choose one — see 04 brief) |

## Quality gate (this document)

- [x] One CTA per email, specific (“Book a 20-minute automation audit”)
- [x] No hard-banned hype words
- [x] Subjects match bodies (E1–E6)
- [x] Same voice; vocabulary only shifts via `{{audience_label}}` branches
- [x] Emotion varies opener/agitation only — arc structure identical
- [ ] Proof points real — **blocked on 01 open questions**
- [ ] `[AUDIT_LINK]` + brand name confirmed
