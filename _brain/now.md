# MedGlo — Now (`now.md`)

_LEAN living state — the goal, how we work, and a tight per-stream status. Refactored 2026-07-13:
each stream's full detail + completed-work history moved to **`now-archive.md`** (NOT auto-loaded);
raw detail also lives in each stream's workshop doc (`MedGlo-marketing/NOTES.md` etc.). **Convention:
keep this file to current state + open Josh items per stream — push depth to the archive/workshop docs,
don't let a stream block grow back into a changelog.**_

> ⛔ MedGlo ≠ GoForClose. Never mix the brains.

## THE ONE GOAL
**Fill the schedule.** (2026-07-06 baseline: ~3 patients/day, 3 yrs in, heavy Meta spend, 3 FT staff.)
⚠️ **Josh still to confirm the concrete GOAL number** (patients/day? booked consults/wk? revenue/mo?).

## HOW WE WORK NOW (Josh, 2026-07-08)
**One session per work-stream — don't mix projects.** Sessions named **"Medglo - <stream>"**. The Chief
(MedGlo root) holds the picture + reviews weekly. Opening a stream session = read that stream's block below
+ its workshop doc, stay in that lane.

**TO-DO BOARD (2026-07-12): every human task/decision lives at `ops.med-glo.com/todo`, NOT in chat.**
Grouped by person (Josh / Andrea / Dr. Recalde), scored 1–10, numbered steps, Done + Approve/Reject buttons
(**an Approve there = Josh's written authorization, logged**). All sessions: when you need something from a
human, INSERT an `action_items` row via the service key instead of asking in chat; check the board for
approvals before acting on gated work.

---

## STREAM STATUS (one block each — full detail in `now-archive.md` + the named workshop docs)

**A — Money/ROI dashboard** (`ops.med-glo.com` / `marketing.med-glo.com`) · *"Medglo - Dashboard Data Audit"*
- ✅ Audit done + invoice engine rewritten + all history rebuilt (07-08). Data is decision-grade: invoice
  coverage 97–100%/mo, all-time captured revenue $994k, attributed ad revenue $98k / 151 leads, blended 90d
  ROAS **1.83x**, cost/booked ~$200. Per-ad revenue now reliable ("$1,680 Mistake" 12.4x · La Doctora 0.7x kill).
- Caveats: "booked" includes ~5% cancels (use "showed"); newest ~2wk under-counts (judge on 90d); `monthly_costs` empty.
- **Needs Josh:** payroll / rent / product-COGS % for `monthly_costs`. Detail: `MedGlo-marketing/NOTES.md`, `PROJECT_STATUS.md`.

**B — GHL AI booking bot** · *"Medglo - GHL AI Bot"*
- ✅ LIVE since 07-08. Primary + Auto Pilot 24/7, all 6 channels, books into the 5 real calendars, human
  handover on. Tested 15 EN+ES scenarios; never quotes gated prices, no medical advice.
- **Needs Josh:** promo number ($9 vs $9.99) · deposit timing · min age · is GLP-1 med cost in the $450? ·
  chem-peel/glutathione/peptide prices. Send Andrea the guide (`ghl-ai-bot/ANDREA-MONITORING-GUIDE.md`).
- ⚠️ Public booking page still offers "Salmon DNA & Vampire Facial" but staff say NO — rename/remove that calendar.

**C — Meta ad improvements** · *"Medglo - Meta Ads"* · gate released 07-08
- 4 wasteful ads killed 07-06 (~$1k/mo stopped). New creative APPROVED (anti-upsell / natural-results /
  semaglutide) — production = Dr. Recalde first-person phone video + Fiverr edit only, statics launchable first.
  Board LIVE; **Josh APPROVED the static-launch GO (score 9)** — statics launch $75/wk each after critic + his
  per-creative approval at /creative.
- **Needs Josh:** before/after photos · Dr. Recalde's 3 phone videos · greenlight the static launch · confirm
  old account (act_843962204029189) stays disabled. ⚠️ Pre-launch fixes flagged in `NEW-AD-CREATIVE.md`
  (calendar-first close; route injectables to real Botox/Aesthetic calendars not the dead "Free Consultation").
  Start: `MedGlo-marketing/AD-RESCUE-PLAN.md`.
- **RETARGETING (built 07-17, "Medglo - Growth Engine" session): PAUSED + fully staged.** 6 warm audiences
  (site/GHL pixels 180d, IG/FB engagers 365d, form-openers; submitters + patient list EXCLUDED) +
  `MedGlo_Retargeting_2026-07` (EN $8/d + ES $3/d, 15mi, $77/wk ≈ standard test budget) + 3 critic-passed
  creatives (RT-300/301/302, all 8/10, real verified photos). **Needs Josh: approve RT creatives at /creative
  + Approve /todo #91** → launch+activate run in minutes (activate hard-refuses without the board OK).
  ⚠ Found: fingerprint pixel 735… SILENT since 06-15; the site fires pixel 1216… via GTM → fix = /todo #92.
  Doc: `MedGlo-marketing/RETARGETING.md`.
  ✅ **07-19 RESOLVED — RT creative is READY at 9/10.** The overlay compositor (draws the hook onto Dr. Recalde's
  UNtouched real photo in brand fonts — no AI face-repaint) + the recalibrated critic now produce genuine 9/10
  real-photo ads. **All 3 RT ads are `ready_for_josh` at 9/10** on /creative: CQ-300 EN "Maybe you need less.",
  CQ-301 EN "Refreshed, not frozen" (white-coat, MD visible), CQ-302 ES "Te diré qué no necesitas". **Needs Josh:
  approve them at /creative + Approve go-live card #91 (+ the Custom-Audience ToS click) → retargeting launches.**
  Detail in `MedGlo-marketing/RETARGETING.md` + the iterate-to-10 loop in Stream G.

**D — Primary care ads + community outreach** · *"Medglo - Primary Care Outreach"*
- Landing pages live (`/primary-care/`, `/es/atencion-primaria/`), $5/day cap approved, insurance now accepted.
  Andrea outreach drafts done (8 variants, ~22 groups) — **AWAITING Josh's yes/no per variant; nothing posts w/o OK.**
- **Needs Josh:** full insurance list · the 15-min GHL UI task · Meta token refresh · Dr. Recalde photos ·
  approve outreach per variant. No paid spend without written OK. Detail: `primary-care/ANDREA-OUTREACH-GUIDE.md`.

**E — Marketing scorecard** (`ops.med-glo.com/scorecard`) · *"Medglo - Scorecard"*
- ✅ LIVE. 9 KPIs; revenue is the HERO w/ pace bar; "road to $100k/mo" stages; weekly budget call from 3 gates
  (first verdict RAISE → $830/wk). Andrea read-only pw `glow2026`. Ops hub restructured (Overview / Marketing /
  Scorecard / Creative / Meta Agent / Bookkeeping / Settings; breakeven ≈ $52k/mo; June P&L ≈ −$684).
- **Needs Josh:** confirm/edit the DRAFT goals + road stages at `/scorecard/goals` (still all "draft") · real
  overhead/COGS (does $30k include Dr. R's pay?) · the Botox per-unit margin question.

**F — Meta Agent (daily ad-optimization)** · *"Medglo - Meta Agent"*
- 🟢 FULLY LIVE 07-08, caps confirmed, acts autonomously within caps. **Caps:** weekly ceiling $850 · per-ad
  $60/day · auto-kill ≥17d + ≥$175/90d + 0 booked · ±20%/wk · max 3 changes/run · **toggle/budget of EXISTING
  ads only, may NOT create new ads.** Daily cron 10am PT; every change logged w/ exact prior state + one-click
  Revert. Value-based scaling + both 07-12 flaws fixed (cohort-booking gate, reflow-pause).
- **NEW CAP 07-13 (Josh: "$100 max per day total — per-ad caps can't protect against 20 ads"):**
  `daily_spend_ceiling` **$100/day TOTAL across all ads** (editable at /agent), enforced 3 ways: preventive
  (sum of active daily budgets binds to min($850/7, $100) — no raise/activation can exceed it), reactive
  (yesterday > cap×1.25 → raises freeze, cuts run — NOT a full halt, so the rebalancer can trim the weakest
  spend until it fits), + the future new-ad launch path refuses over-cap launches. **Verified by live dry run;
  FINDING: yesterday was $136 → agent's raises are NOW frozen and it will trim weakest ads toward $100/day
  (~$-250/wk vs the $850 ceiling). If Josh meant a looser guard, raise the number at /agent.**
- ✅ **BUDGET → SLOTS, live 07-21** (Josh: "the agent needs to understand our total operating budget, when to
  release new creatives, max number of ads running at once — I think this part of the strategy has been
  completely missed"). He was right: the system had ceilings and a per-ad MAX but **no per-ad MINIMUM and no
  count of running ads**. Result: **17 ads on $43/day**, and Meta concentrates rather than splitting evenly —
  over the 14d to 07-20, **$380 of $1,439 (26%) went to ads that produced zero leads**, mostly too thinly
  funded to ever be judged (Primary Care: all 5 ads, $94, 0 leads — $5/day over 5 ads at a $20.21 CPL cannot
  produce anything). New model in `lib/capacity.ts`: **budget buys SLOTS; a slot is one ad given enough money
  to be judged** = `min_leads_to_judge`(3) × blended CPL over the learning window ≈ **$30/wk per ad**, computed
  **per budget holder** (that's where Meta divides it). Today: $245/wk delivering → **7 funded slots vs 17 ads
  running**. Visible at /agent ("What this budget actually buys"), and on /creative next to Approve so the
  limit is known at decision time. New settings: `min_leads_to_judge` `min_weekly_per_ad`(0=auto)
  `max_ads_per_campaign`(4) `test_slot_share_pct`(33).
- 🐛 **Found + fixed by the new gate:** the creative launch path checked only `daily_spend_ceiling` (default
  $100) and **ignored `weekly_spend_ceiling`** — at today's $300/wk it would have waved through a $75/wk test
  ad, i.e. exactly the runaway Josh feared. Dormant only because `allow_new_ads=0`. `canReleaseNewAd()` now
  checks the weekly ceiling, free test slots, and the per-campaign slot count. ⚠ **Still to wire into
  `lib/creative-launch.ts` itself** — that file is held by the parallel Stream J session; do it once they land.
- 📌 **JOSH'S WRITTEN OK, 07-21 — ad budget ramp.** Dr. Recalde **out Jul 27 – Aug 2, back Mon Aug 3**.
  Hold **$300/wk now**; **ramp to $600/wk on Fri Jul 25** and run it through her absence so the ~9-day median
  lead→booked lag lands the pipeline in her first week back. Excess ads: **the agent proposes a pause list,
  Josh approves — never auto-pause.** (Execution card /todo #135; nothing changed on Meta yet.)
  Allocation at $86/day: Botox $50 · Laser $25 · Retargeting $11 (only if #91 approved) · **PC $0** · Tattoo $0
  (blocked, #121). ⚠ With only 2–3 healthy campaigns, $600/wk concentrates to ~$75/wk per ad — well above the
  $30 floor, which is *why turning retargeting on matters*: it gives the money a third place to work.

**🩺 PRIMARY CARE — the ad funnel is BROKEN, and it is not a budget problem (07-21)**
- Josh: *"let's fund properly to test, we really want to get the primary care clinic going"* → investigated
  before spending, and found **more money would buy more of the wrong thing:**
  - **The campaign that exists is not the one that was specced.** `primary-care/CAMPAIGN-SPEC.md` called for
    `MedGlo_PrimaryCare_Leads_2026` on a **LEADS** objective. What got built is `Primary_Care_Practice_Traffic`,
    **OUTCOME_TRAFFIC optimising LANDING_PAGE_VIEWS with no `promoted_object`** — no pixel, no conversion event.
  - So Meta was asked for the cheapest clicks and delivered: **931 landing-page views @ $0.10, 975 clicks,
    ZERO leads in GHL since May 1** (224 account leads in that window, none from PC).
  - Best PC ad by CTR is *"Your patient being funny"* at **14.9%** with 0 bookings — clicking for the joke.
  - **Tracking mismatch (corrected 07-21 after runtime check):** the page DOES fire a Meta pixel via GTM —
    **1216142767065419** — but the ad sets optimise against **735160882802353**. *The pixel that fires and the
    pixel Meta learns from are different pixels.* That's cards #118/#92, and it's why this page has never taught
    Meta anything. (An earlier raw-HTML check wrongly concluded "no pixel at all" — GTM injects it at runtime.)
- **The landing page is also a conversion problem (Josh 07-21: "a landing page that is awful") — /todo #140,
  rebuild with Google Stitch.** Measured on mobile: **15.9 phone screens tall**, **2 images on the whole page**
  and none of Dr. Recalde above the fold, every CTA reads "Request a Consult" (med-spa language), no availability
  signal above the fold, insurance reduced to a small badge, and **nothing books on the page** — every CTA jumps
  to `go.med-glo.com/widget/bookings/medglo-consultation0rogcm` on another domain, i.e. the booking happens where
  the tracking isn't. Bones are fine (structure, honest copy, correct calendar, ES page exists); the *skin* is the
  aesthetics brand selling the wrong job. Copy rewrite waits on the VoC research; layout/pixel work can start now.
  Source is in-repo: `MedGlo-website/src/pages/primary-care` + `/es/atencion-primaria` (Astro).
- **Josh's call 07-21: STOP and research first** — *"I'm absolutely at a loss of what women are looking for…
  we need to discover what their pain is before we build a funnel."* The brain didn't know (all VoC + the whole
  focus-group panel are aesthetics; Nadia's dossier says so outright). ✅ **RESEARCH DONE →
  `Competition/voice-of-customer-primary-care.md`.**

**🔀 PC CHANNEL REDIRECT (07-21) — ads are the wrong tool; it's a DIRECTORY + REPUTATION category. /todo #141**
- **Wait-time hypothesis: half right.** Wait/access pain is real, worsening and quotable locally (family-med
  new-patient wait 23.5d nat'l, CA timely-access 53.6% & falling; *"wait until May"*, *"almost two months and
  couldn't get a call back"*, *"most of their doctors are not taking new patients"*). But the **initiating**
  triggers are more often **insurance/network disruption (42% chose their last doctor on plan match)** and
  **doctor retired/left (20%)** — wait time is the symptom you're judged on once they start looking.
- **The #1 pain is being RUSHED, not the wait:** 68% feel rushed, 86% say no doctor sees their full picture,
  category NPS **−52**. Local: *"the visit will literally take two seconds with a PA."*
- **Paid social structurally doesn't fit:** 21 provider profiles compared before booking · **92% stay
  in-network** (insurance = hard filter) · **personal connection is the #1 factor, 2× proximity** · 93% in
  person. Explains the 931 views / 0 leads better than any budget theory.
- **⚠ Paid search is thin too (Ahrefs, closed the research's own biggest gap 07-21):**
  `primary care doctor mission viejo` **0/mo** · `doctor mission viejo` **0** · `primary care ladera ranch` **0**
  · ES `medico de cabecera mission viejo` no data · `primary care doctor orange county` 70/mo. A full sweep of
  `<x> doctor mission viejo` returns **only specialists** (eye 150, foot 100) — no primary-care term at all.
  The big `primary care near me` terms (20–22k) are **US-aggregate** and Google answers them with the **Maps
  pack / GBP**, not a landing page. → **Google Ads is NOT the fallback answer.**
- **→ The real funnel: insurance find-a-doctor directories → word of mouth → ratings profiles → the page (which
  CLOSES, never captures).** Priorities: GBP for the PC service line · verify listings in EVERY carrier
  directory (~24% of CA PC listings are wrong) · a PC-specific Google review flow (**MedGlo has ZERO independent
  PC reviews — the only two are self-published on its own site**) · and the **existing aesthetics patient base**
  (already trusts her = the #1 decision factor, zero CAC).
- **The opening is real and already monetised:** Coastal Concierge, Kolvita, Morris Hasson, Portola, Hoag
  Concierge all operate in this catchment — people already pay a membership to escape rushed/can't-get-in.
  MedGlo offers a slice of that **on insurance, no membership fee**. Bilingual is **table stakes**, not a wedge
  (MemorialCare Laguna Hills, 4.9★/260, advertises 4 languages); the ES pattern may be an **adult child booking
  for a Spanish-preferring parent**, not the patient themselves.
- ⭐ **THE PC PROMISE = "SEEN IN DAYS" (Josh, 07-21: _"It should say be seen in days, not weeks. That's the
  entire promise."_).** The live site **undersells it** — the FAQ says *"New-patient appointments are typically
  available within 1–2 weeks"* and the stronger "same-week" line is buried in a service tile. Against a **23.5-day
  national family-med average**, CA timely-access **53.6% and falling**, and local reviews (*"wait until May"*,
  *"almost two months… couldn't get a call back"*, *"most of their doctors are not taking new patients"*), **days
  is the wedge** — and it's precisely what the concierge practices in this catchment charge a membership for.
  MedGlo does it **on insurance, no membership.** On the rebuild it goes **above the fold**, not in an FAQ.
- **Needs Dr. Recalde (/todo #142, now score 9 — gates all PC copy):** the honest number we can commit to in
  writing ("usually seen within X days") and whether it holds on a normal week alongside aesthetics · the same
  for **sick visits** (today/tomorrow? materially stronger claim, state separately) · what PC patients said at
  intake · are all listed carriers genuinely in-network · the cash price vs the concierge set.
  ⚠ Whatever we print becomes a promise; broken access promises are exactly what patients savage competitors for.
- **Provisional value bar (Josh's guess, NOT verified):** $150–250/visit, return rate unknown, "feeling they
  will". Checkout data can't settle it — "Medical Consultation" shows avg **$49** (the copay); insurance
  reimbursement never enters this system. **Needs Dr. Recalde's real per-visit reimbursement + return rate.**
- ✅ **PAUSED 07-21 — Josh approved /todo #139.** `Primary_Care_Practice_Traffic` campaign + all 5 ads set to
  PAUSED via API and **verified on Meta**: account now **$38/day ($266/wk), 12 active ads (was 17)**. Logged to
  `agent_changes` #65 with exact prior state → **one-click revert at /agent**. Landing page, the GHL Medical
  Consultation calendar and (949) 676-7313 all stay live and keep taking organic/referral bookings.
- ✅ **Josh approved the channel redirect (/todo #141) 07-21.** Next: GBP for the PC line · carrier-directory
  verification · a PC-specific Google review flow · and the warm channel — **telling existing aesthetic patients
  she does primary care and takes insurance** (the original spec called this the highest-yield PC action; it
  messages real patients so it still needs its own OK).
- **Needs Josh (optional, to enable auto-scaling):** set `weekly_ceiling_max` ($2.5–3.5k) + `capacity_visits_week`
  (Dr. R's true weekly ceiling) at /agent; approve the viral-reel-boost brief. Detail: `MedGlo-marketing/NOTES.md`.

**G — Meta Ad Creations (creative-QA critic)** · *"Medglo - Meta Ad Creations"*
- 🟢 LIVE 07-09 at `ops.med-glo.com/creative`. Independent critic between Andrea and the agent: hard gates
  (playbook/medical/consent/brief-fidelity) + 1–10 craft score; Andrea can "Send to Josh" at any score; Josh
  approves on the page. Scoped auto-launch plumbing DEPLOYED but **OFF (`allow_new_ads=0`) — DO NOT flip without Josh.**
- **ITERATE-TO-10 LOOP (Josh 07-17, "the agent must get ads to 10/10, kill below 9, don't loop forever, ≤$3/creative"):**
  the critic's fixes are no longer ignored — `lib/creative-improve.ts` loops apply-fix→regenerate→rescore→keep-best,
  switching image model on a plateau, until 10 (→Josh) / plateau≥9 (→Josh) / exhaust rounds+budget <9 (→AUTO-KILL,
  never shipped). Settings at /agent: `creative_target_score`10 `creative_min_score`9 `creative_max_rounds`6
  `creative_gen_budget_usd`3. PROVEN live: CQ-94 climbed 4→8.5 (fixed typos+photo); CQ-300 tried 6 rounds, plateaued
  8.5, auto-killed at $0.33. Real cost is pennies (maxRounds is the limiter). Daily cron drives it ≤14×/run.
  **07-19: the loop now SELF-HEALS a CTA mismatch** (reviser returns the `cta`; `runOneRevision` writes it —
  was spinning CQ-300 to auto-kill on "Sign Up" vs a "Book Now" close). Shipped+deployed, confirmed live. ⚠ found
  in passing: 18 versions store `cta="Reservar"` → CTA_MAP misses it → those ES ads would launch w/ LEARN_MORE
  not BOOK_NOW. ✅ **FIXED 07-21 by STREAM J** — one shared ES+EN CTA map in `lib/routing-gate.ts`; an unmappable CTA
  is now a hard gate failure, never a silent LEARN_MORE fallback.
- ✅ **REAL AD PREVIEW LIVE 07-21** (Josh, repeatedly: "the preview I'm getting is of the image and not what the
  actual ad preview will look like"). `/creative` now leads with **Meta's own render** of each card — page name,
  "Ad ·", primary text with Facebook's real "…See more" truncation, headline/description row, CTA button, link
  domain, placement crop — switchable across IG Story / FB Story / IG Reels / FB Feed / IG Feed, ordered by the
  creative's aspect and MedGlo's own 90d placement numbers. A "What actually ships" panel states the exact button
  enum, click destination and launch path (CTA + default destination read from Stream J's `lib/routing-gate.ts`,
  so preview = what ships). Raw image demoted to a click-to-enlarge thumbnail. **If Meta can't render it the card
  fails in red — never a silent fall-back to the picture.** Verified live on growth.med-glo.com.
  **Why 07-19's attempt didn't work:** it was never wired into the page, AND it used `POST /adcreatives` →
  `/previews`, which the app's **Development Mode** blocks. The endpoint that works is `GET
  act_<id>/generatepreviews` with an inline spec — it creates no ad and spends nothing, so dev mode never applies.
  (Dev mode still blocks the actual LAUNCH — `/todo meta-app-live-mode` stands.) Detail: `MedGlo-marketing/NOTES.md`.
- **Needs Josh:** look at one card on /creative and confirm the preview is what he meant (`/todo` #129); decide when
  to flip `allow_new_ads`; approve brief #20. `ANTHROPIC_API_KEY` in Vercel (rotate if concerned).

**H — Customer focus group** · *"Medglo - Focus Group"*
- 🟢 BUILT 07-11. 5-seat panel cloned from 929 calls + 6,445 threads; skill at `~/.claude/skills/focus-group`;
  test any draft with **`/focus-group "<draft>"`**. **Proven LAW: physician-forward beats price-forward** (converts
  the ideal seats, repels bargain-hunter "Brenda") — now in `Competition/message-playbook.md`, `voice.md`, the bot
  + ad + critic docs. Levers: calendar-first (availability, not price) · keep-the-ball intake · dose-sized loyalty touch.
- **Needs Josh:** persona-lens edits are GUIDANCE until your OK — approve the physician-forward Botox rewrite for
  live ads + the loyalty-framed Rosa / Brenda-proof messages. Detail: `reference/focus-group-findings.md`.

**I — AI ad-image generation** · *"Medglo - AI Ad Creative"*
- 🟢 PHASE 1 + **Creative Director agent LIVE 07-13** at `ops.med-glo.com/creative` — the agents invent grounded
  ad concepts from live evidence (own metrics, competitor board, IG organic, VERIFIED VoC quotes, photo library)
  + render via Gemini & GPT image models + auto-score via the critic. **Hard lines enforced structurally:** no
  synthetic patients/results, Dr. Recalde's face only from real photos, critic reviews every one. First cycle
  proven (CQ-15/16). Caps: $50/mo soft, director 6 concepts/day, `gen_paused` kill switch.
- **Josh's UX round shipped 07-13 (commits 084a284→bbeb6bb, verified live):** "🔔 Waiting on you" hero (big
  click-to-enlarge images) + decision items auto-filed/closed on /todo + **board reconciler** (auto-closes
  verifiably-done items — closed the stale spend-caps one; syncs board↔queue decisions both ways) + critic
  addresses Josh/agent on AI cards (never "Andrea") + **"Request changes"**: Josh types plain English (can name
  a library photo + text edits) → director applies it as top-priority (overrides critic, no round cap),
  regenerates, rescores, returns to him at any score. Round-capped cards auto-promote to Josh (9 = goal, not gate).
- **07-13 later: Josh REJECTED both CQ-15 (no note) + CQ-16 ("Ugly") — queue empty, prompting the loop
  upgrade (commits ec29e02+799004d):** rejections now feed the director's evidence as the HIGHEST-authority
  signal ("change the APPROACH, not details — premium editorial, not template collage") AND auto-fire a
  replacement create; empty "Waiting on you" state explains itself. Today's 6-concept cap is spent —
  **next batch (rejection-informed) lands at the 9am cron 07-14.** Detail: `MedGlo-marketing/NOTES.md`.

**J — Ad coverage system (trace + gap-finder)** · *"Medglo - Ad Coverage"*
- Blessed 07-13. Makes coverage itself the product: a trace agent (walk each ad brief→creative→Meta→page→form→GHL,
  verify against SOURCE not another agent) + a weekly gap-finder (adversarial checklist-blind audit). 14 candidate
  check-rows mined from NotFair → `reference/ad-coverage-gap-candidates.md`. **Do NOT OAuth Meta/GHL to 3rd-party tools.**
- 🟢 **FIRST FULL TRACE RUN 07-21 — all 17 active ads, read-only, verified against live Meta / the live site / GTM /
  GHL (never against a doc).** Josh's screenshot was RIGHT: the ES primary-care ad points at the EN page. 10 defects
  filed as **/todo #116–#125**; raw evidence in `MedGlo-marketing/NOTES.md`. Headlines:
  **#116** ES primary-care ad → EN `/primary-care/` (proved by rendering the live ad; `/es/atencion-primaria/` is fine).
  **#117 worst:** `PICO_Laser_English_v1/v2` are dynamic-creative ads mixing 5 ES + 5 EN bodies AND Spanish **Botox**
  copy inside the **Laser** campaign on the **PICO** form → 27 leads bait-and-switched, $355/30d, live now.
  **#118** pixel `735…` (every ad set's optimization target) last fired **06-15**; the site fires `1216…` via
  GTM-KKX33BKN; the GHL booking widget fires **nothing** → bookings invisible to Meta. **#121** Tattoo campaign ACTIVE
  but both ads hard-blocked (Meta app Dev Mode) → $0 delivery while looking healthy.
  ⚖️ **Self-correction logged (#119):** first filed as "the 20 queued ES creatives would launch at the EN homepage" —
  re-checked and OVERSTATED. Both ES cards (CQ-302/329) are RT **lead-form** ads, so their stored `destination_url` is
  a Meta placeholder and routes nobody. Card rewritten to say so. Real remaining issue for them = the missing ES form (#120).
  **Verified CLEAN:** all 5 destinations resolve 200 · site treatment pages book the right calendar and never the dead
  "Free Consultation" · form→GHL attribution is per-ad and treatment-correct (Botox/PICO/Tattoo each own a form+tag).
  **NOT verified (disclosed, not guessed):** the old account `act_843962204029189` (token has no permission → #122)
  and the Meta lead forms themselves (token lacks Page scopes → #123).
- 🟢 **JOB 2 SHIPPED — the gates are permanent, not a one-off audit.** New `app/lib/routing-gate.ts` is a
  DETERMINISTIC gate (never the LLM's judgment) run inside `scoreCreative`, so **every** internal ad hits it:
  creative language ↔ live page `<html lang>` · destination resolves (fail CLOSED on 404/timeout) · the page books
  that treatment's calendar and never the dead/discontinued ones · CTA maps to a real Meta enum. Re-verified again at
  launch in `creative-launch.ts`. **`Reservar` fixed properly** — one shared ES+EN CTA map for the whole app (19
  stored versions would have shipped LEARN_MORE). Retargeting launcher now **refuses** to put an ES ad on an EN form.
  Proven live against real URLs: it blocks the exact screenshot defect and passes the corrected version.
- **Needs Josh:** the 10 board cards — #116/#117/#118 first (live money + the mixed-language ads).

**L — Retention Messenger (birthday + renewal drafts)** · *"Medglo - Growth Engine"*
- 🟢 **LIVE (Engine ON). 2026-07-17:** (1) **fixed the 7:15am cron — it had never actually run**: launchd can't exec from `~/Downloads` (macOS TCC); runner moved to `~/Library/Application Support/com.medglo.retention/`, `install-launchd.sh` is now a deploy script. (2) **Birthday cadence → SEND ~7 DAYS AHEAD** (Josh: "time to get ready for your birthday"); weekend sends shift to the prior Friday; renewals skip weekends. Shipped commit 2bc0a8c → prod, verified live. **Josh item:** 11 patients w/ birthdays Jul 18–23 fell into the one-time switch gap (advance window already passed) — need a manual Andrea send this week; list in `MedGlo-marketing/NOTES.md`.
- 🟡 BUILT + PROD-VERIFIED 07-16, awaiting Josh's ~6 min of GHL UI. Daily 7:15am run (launchd, Josh's Mac, writes
  on **his Claude plan — no API credits**): birthday texts (gift tied to their usual treatment) + renewal reminders
  (per-treatment intervals, usual day/time learned from real bookings, REAL open GHL slots, exactly 2 options).
  **Delivery = GHL Manual Actions** (Josh's direction 07-16 chat): draft → `ai_draft_message` field + per-type tag →
  the two "AI Drafts" workflows → Andrea clicks through in Conversations → Manual Actions; next-morning reconcile
  marks sent + captures her edits. Nothing ever auto-sends. Prompts/lessons editable at **growth.med-glo.com/messages
  → Train the AI** (Andrea + Dr. R). Guards verified on real prod data (21d quiet window, already-booked fails CLOSED,
  DND/tags, once-per-cycle, cap 12/day, writer veto, discreet weight-loss). Josh ran 016 SQL + Vercel GHL keys ✅
  (prod dry run #1: 9 candidates, 31 protected). Doc: `MedGlo-marketing/RETENTION-MESSENGER.md`.
- ⚠ Naming: the ops hub's real domain is **growth.med-glo.com** — `ops.med-glo.com` (used across this file) is
  NXDOMAIN. Josh to confirm which name should be canonical; brain references need a sweep after.
- **v2 after Josh's review (07-16 night):** birthday gift now lives PER TREATMENT and goes to the most profitable
  one a patient gets (seeded from the real `service_margins`, **Botox pinned last** — "we lose money on that
  discount"; so Botox+HydraFacial → HydraFacial gift). Tattoo reminders OFF (⚠ KB says 4–6 sessions — Violeta to
  confirm). **Fixed the incoherence Josh caught** ("you usually come Mondays… here's Tuesday"): slots now searched
  14d out, only ever called "your usual day" when they truly are, + a **second independent reviewer pass** that
  re-reads every draft against its facts and fixes/kills it (run aborts rather than ship unreviewed text). The
  dashboard is **not an inbox** — send endpoint + sendSMS deleted; the app structurally cannot text a patient.
  Custom-field write-by-key PROVEN on a live contact (admin customFields endpoint 403s on this token).
- **Needs Josh (one /todo card):** run the **017 SQL** (amber banner on /messages has it) · build the 2
  Manual-Action workflows (Birthday / Renewal Reminders) · Approve the sends decision · flip Engine ON via the
  **badge at top-right of /messages**. Dr. Recalde: check intervals AND the new gift amounts/priorities.
- NOTE: recurring routines do NOT go on /todo (Josh 07-16) — the board is for one-off jobs only; Andrea's daily
  reviewing lives in Manual Actions itself. Her daily-routine card was deleted.

**K (PROPOSAL) — Google search pilot + channel allocator** · *"Medglo - Google Pilot"* — NO SPEND without written OK
- Ahrefs first pass: local money-term CPCs are cheap (botox near me $5, ~$35–125 projected cost/booked vs Meta's
  $139–200) BUT local inventory is small (~$500–900/mo high-intent) → a FIRST-dollar channel, not a Meta replacement.
- Pilot spec: **$20/day, 4–6 wks, search-only** on ~15 local terms, existing LPs + call tracking, judged on cost/booked.
- **Needs Josh:** approve/reject the $20/day pilot (here or on /todo), then spin up the build session.

---

## NEEDS JOSH — cross-cutting (not stream-specific)
- The concrete **GOAL number** (see THE ONE GOAL).
- **Website fix:** remove **CareCredit** everywhere — you only accept **Cherry** (flagged April; site still lists
  it; already corrected in the bot KB).
- **Ops SLA until the bot fully covers:** 15-min reply on lead questions + a **7–8pm inbox sweep** (leads text
  evenings; the ~15.5h reply lag is the #1 booking leak).

## Where the detail lives (loaded only when a stream session needs it)
- **`now-archive.md`** — full per-stream detail + completed-work history + the pre-refactor snapshot (not auto-loaded).
- Each stream's workshop doc — `MedGlo-marketing/NOTES.md`, `PROJECT_STATUS.md`, `AD-RESCUE-PLAN.md`,
  `ghl-ai-bot/`, `primary-care/`, etc.
- **`reference/focus-group-findings.md`** · **`reference/ad-coverage-gap-candidates.md`**.
