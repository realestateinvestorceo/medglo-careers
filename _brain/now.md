# MedGlo — Now (`now.md`)

_The running state. Keep it short — prune when stale._

> ⛔ MedGlo ≠ GoForClose. Never mix the brains.

## THE ONE GOAL
**Fill the schedule.** 2026-07-06: only 3 patients in a day, 3 years in, heavy Meta spend, 3 FT staff.
Josh still to confirm the concrete target (patients/day? booked consults/wk? revenue/mo?).

## HOW WE WORK NOW (Josh, 2026-07-08)
**One session per work-stream — do NOT mix projects in one session.** Sessions are named
**"Medglo - <stream>"** so Josh can spot them in his window. The Chief session (MedGlo root) holds
the picture and reviews everything **weekly** (scheduled) to propose new sessions where we're
off-goal. When Josh opens a session for a stream, read that stream's block + its workshop doc,
and stay in that lane.

---

## STREAM A — Money/ROI dashboard (`marketing.med-glo.com`)   ← session "Medglo - Dashboard Data Audit"
**Josh's driver (2026-07-08):** Calysta pull correct? where does the data go? right contacts matched to the right Meta ads?
**✅ AUDIT DONE + REVENUE ENGINE FIXED 2026-07-08 — GATE RELEASED for Stream C.**
(Two passes: read-only audit in the Meta-Ads session, then the dedicated Dashboard-Data-Audit session
independently re-verified it, found the ROOT CAUSE of broken revenue, rewrote the scraper's invoice
engine, and rebuilt ALL historical invoice data from the EMR overnight. Raw detail:
`MedGlo-marketing/NOTES.md` §2026-07-08; trust table in `MedGlo-marketing/PROJECT_STATUS.md`.)

**TRUST — verified to source:**
- **Ad spend** — fresh (pulls yesterday each 7am), continuous 13 mo, no dupes/holes; per-ad totals match the Ads-Manager-checked 07-06 numbers. Prod Meta token alive.
- **Lead→ad match** — verified against ALL 7,547 live GHL contacts: 0 mismatches; 989/997 ad-named leads join a real Meta ad_name. Contacts ARE tied to the right ads (Josh's core worry: answered YES).
- **Lead→patient match** — 25/25 sampled pairs same person (phone AND email agree); 0 false positives in all 152; the risky name-fuzzy fallback has never actually fired.
- **Booked / Showed / cost-per-booked** — real EMR appointments. 90d: cost/booked ≈ $200, cost/showed ≈ $215. Dashboard math re-computed independently = digit-identical to the site.
- **Revenue / ROAS / margin table — NOW FIXED AND REBUILT (was structurally wrong, NOT healable).** Old scraper summed the patient page's 3-newest-undated-invoices onto the newest visit: double-counted repeat patients, collapsed recurring GLP-1 payments, counted unpaid invoices, froze Mar–Jun. Rewritten 2026-07-08 to read the EMR's full DATED per-invoice history (paid amounts only, allocated to the right visit); overnight backfill rebuilt all ~930 patients. **FINAL STATE (verified on the live site): invoice coverage 97–100% every month; all-time captured revenue $994k (was $142k, partly double-counted); attributed ad revenue $98k across 151 matched leads; blended 90d ROAS 1.83x real (the old 0.84x was an artifact); cost/booked $200.** Per-ad revenue is now decision-grade: e.g. "$1,680 Mistake" 12.4x, Skip the Chains 2.6x, La Doctora 0.7x (kill validated).

**Caveats that remain:** "booked" includes booked-then-cancelled/no-show (~5%) — "showed" is the strict metric; newest ~2wk under-count (11-day lead→appt lag) → judge on 90d; 112 organic-FB leads sit in "Unattributed"; monthly_costs still empty (P&L "Net" only subtracts ad spend until Josh supplies payroll/rent/COGS); margin table treats Botox as $0 margin by design.
- **Needs Josh:** payroll / rent / product-COGS % for `monthly_costs`.

## STREAM B — GHL AI booking bot   ← session "Medglo - GHL AI Bot"
- **State: ✅ LIVE since 2026-07-08 (a day early).** "Appointment booking bot" = **Primary + Auto Pilot,
  24/7**, all 6 channels (SMS/IG/FB/Chat Widget/Live Chat/WhatsApp). KB attached (Bot Training trigger),
  playbook-voice prompt, booking into the 5 real calendars (Botox / Aesthetic Consultation / PICO /
  Tattoo-consult / Medical Consultation — NOT "Free Consultation", which turned out to have 0 real
  appointments ever). Human Handover ON (3 scenarios → assign Andrea + task + tag); Andrea takeover =
  just reply manually (bot sleeps 2h in that thread). Reschedule enabled; cancel stays human.
  **Tested: 15 EN+ES scenarios** — all gap topics hand off (never quotes promo/tattoo/peel prices,
  min age, GLP-1 med inclusion), no medical advice, booking offers exactly 2 real slots. One language
  bug found+fixed in testing. Raw log: `MedGlo-marketing/ghl-ai-bot/NOTES.md`.
- **Andrea's 1-page guide:** `MedGlo-marketing/ghl-ai-bot/ANDREA-MONITORING-GUIDE.md` (watch, take over,
  log wrong answers → trained in weekly). Josh: send it to her.
- **Needs Josh (bot hands these to a human until answered):** public Botox promo number ($9 vs $9.99);
  deposit mention timing; min age; is GLP-1 med cost in the $450?; chem-peel/glutathione/peptide prices.
- **Watch (first week):** first real bot booking → confirm the confirmation/reminder workflow fires;
  weight-loss threads (med-inclusion answer defers to consult); weekly training pass from Andrea's log.
- **Flag:** public booking page still offers "Salmon DNA & Vampire Facial" calendar but staff say NO
  vampire facial/PRP — bot answers correctly; the page contradicts it. Rename/remove the calendar.

## STREAM C — Meta ad improvements   ← session "Medglo - Meta Ads" · **✅ GATE RELEASED 2026-07-08 (Stream A verdict posted)**
**Cleared to start.** Primary metric: **cost per booked/showed** (≈$200/$215 at 90d). **UPDATE (07-08 ~05:45):
revenue/ROAS are now ALSO decision-grade** — invoice engine rewritten + ALL history rebuilt from paid EMR
invoices; coverage 97–100% every month (see Stream A). **RE-PULL all per-ad numbers before deciding — they
changed materially** (90d: "$1,680 Mistake" 12.4x · Skip the Chains 2.6x · La Doctora 0.7x/kill validated ·
blended 1.83x). Pre-March history exists now. Deliverables: confirm the right ads are running after the
2026-07-06 kills, and give Josh **exact ad copy** for what runs next.
**Note:** account-verification needs the live Meta token (blank in local `.env`) — Josh must paste it or do the System-User steps in PROJECT_STATUS.md. Rescue-plan per-ad numbers RECONCILE vs live (La Doctora $533/28 leads/0 booked; Pico reel $483/17/0 booked — both confirmed 0-booked losers).
- **State:** 4 wasteful ads killed 2026-07-06 (5 ad toggles OFF; ~$1k/mo stopped — the 2 live spenders
  were "La Doctora" Spanish $533/30d and "We used our Pico" reel $500/30d). New creative APPROVED
  (anti-upsell, natural-results, semaglutide) — copy written; production plan = Dr. Recalde first-person
  phone video, Fiverr for editing only, NO influencer, static image ads can launch first. Budget
  reallocation authorized but NOT executed (held until creative exists).
- **Next session's job:** build the 3 new campaigns **PAUSED** (static versions launchable now, video
  when shot); execute the budget scaling and log it; judge everything on **cost per booked**, not CPL.
- **Start here:** `MedGlo-marketing/AD-RESCUE-PLAN.md`, `NEW-AD-CREATIVE.md`, `ad-production-guide.md`.
- **Needs Josh:** before/after photos (or "use the site's"); Dr. Recalde's 3 phone videos; greenlight the
  static launch; confirm old "MedGlo" account (act_843962204029189) is still disabled (MedGlo3 is active).

## STREAM D — Primary care ads + community outreach   ← session "Medglo - Primary Care Outreach"
- **State:** Landing pages live (`/primary-care/`, `/es/atencion-primaria/`); Josh approved "go for it",
  **$5/day cap**; website PR #103 merged. Insurance now accepted for primary care (was cash-only until ~June).
- **Community outreach via Andrea — DRAFTS DONE 2026-07-08, AWAITING JOSH's yes/no per variant.**
  Deliverable: `MedGlo-marketing/primary-care/ANDREA-OUTREACH-GUIDE.md` — 8 post variants (A warm
  intro · B empathy · C meet-the-doctor · D business-share-day · E comment-reply · F mom-group ·
  G/H Spanish), ~22 target groups across MV/Ladera/RSM/Lake Forest/Aliso Viejo + Latinos en OC,
  6-week cadence, comment/DM playbook (route to (949) 676-7313 / med-glo.com/primary-care, manual
  GHL entry for DM leads), don'ts. Etiquette research confirmed Andrea-as-herself-with-disclosure
  is the right shape; mom groups mostly promo-thread-only. Both landing pages re-verified live;
  all claims match the page (1–2 wks new patients, same-week *effort*, adults 18+).
  **NOTHING POSTS until Josh writes OK per variant here.**
- **Also next:** build GHL workflows (`primary-care/GHL-SETUP.md`), refresh Meta token, build campaign PAUSED,
  Josh activates. **No paid spend until Josh's written OK here.**
- **Needs Josh:** full insurance list; the 15-min GHL UI task; Meta token refresh; Dr. Recalde photos.

## STREAM E — Marketing scorecard   ← session "Medglo - Scorecard"
- **✅ LIVE 2026-07-08: https://marketing.med-glo.com/scorecard** — 9 KPIs, each with last-week value,
  goal line, green/yellow/red, 12-week trend bars. Mobile-tested. Weekly ritual printed on the page
  (Mon 15 min, Josh + Andrea, one action per red tile). **Andrea's read-only password: `glow2026`**
  (opens ONLY the scorecard; the admin password still opens everything).
- **Reply-speed + waiting-on-reply KPIs REMOVED 2026-07-08 (Josh: measurement unreliable for now).**
  Was 11 KPIs, now 9. The **main dashboard's "is anyone answering?" follow-up panel was ALSO removed
  2026-07-08** (Josh is sharing the dashboard with Andrea + reply-time metric has the automated-send
  accuracy caveat). The `lead_followup` sync + table still run daily — data is intact, only the two
  UI surfaces are gone; easy to restore or move to an internal-only page later.
- **V2 SHIPPED 2026-07-08 (Josh's direction):** revenue is now the HERO — this week vs weekly goal with
  a pace bar ("through Tue, you'd want ~$X by now"), fixing the last-week/this-week confusion (all big
  numbers labeled "last week"; pace lines account for the ~1-day sync lag). Added **the road to $100k/mo**
  ($12k → $16k → $19k → $23k/wk = $100k/mo where a hired physician becomes affordable → $30k/wk = Dr. R
  steps back — DRAFT, Josh to confirm) + **weekly budget call** (RAISE/HOLD/CUT next week's ad spend from
  3 gates: cost/booked ≤$200 4wk · 90d ROAS ≥1.5x · show ≥85%; advisory only, Josh executes — this exact
  rule is what the future ads agent will run, so its moves stay auditable) + **actions list** (per-ad
  moves from live 90d data + one fix per red tile). First live verdict: **RAISE → $830/wk** (all gates
  pass: $139/booked, 1.8x, 93%).
- **GOAL MATH (draft for Josh):** clinic reality post-rebuild = ~$46-50k/mo, avg ticket $313, trailing
  4wk $11k/wk. At ~55% est. margin with $30k/mo overhead (Josh's rough number, seeded into monthly_costs
  Jan–Dec 2026 → P&L "Net" is live) + ~$30k/mo replacement physician: **$100k/mo ≈ break-even for hiring
  the physician; ~$130k/mo = comfortable step-back.** $100k/mo = ~74 visits/wk (12/day) at current ticket.
- **DRAFT GOALS (Josh to confirm/edit at /scorecard/goals):** leads 26/wk · lead→booked 15% (now 12%) ·
  show rate 85% (now 93%) · new patients 11/wk (now ~9) · primary-care visits 3/wk ramp (north star
  25/wk = 5/day; now ~0) · revenue $12k/wk (= road Stage 1; bump this goal to advance stages) ·
  ad budget ≤$800/wk (budget call moves it) · cost/booked ≤$200 (audited 90d actual) ·
  +2 Google reviews/wk (count = manual weekly entry by Andrea).
- **AD-TABLE FIX 2026-07-08:** Josh confused why an ad read CUT (top profit table) vs REVIEW (bottom
  funnel table). The bottom table now judges **cost per booked** (EFFICIENT/OK/EXPENSIVE/NO BOOKINGS,
  col "Booking efficiency") instead of raw ROAS — two clear lenses (booking efficiency vs profit
  margin), not a contradiction.
- **✅ BOTOX-MARGIN FIXED 2026-07-08 (Josh: Botox ~$5/unit cost, ~$10 sale = 50%, NOT $0).** The engine
  had Botox HARDCODED out of profit (info-only bucket); now it contributes at its product margin
  (neurotoxin 50%, editable). Effect: "$1,680 Mistake" −$264 CUT → **+$3,323 SCALE** (now agrees with
  funnel EFFICIENT + scorecard); La Doctora −$1,132 → +$500 (lifetime ~breakeven — recent funnel/actions
  still flag it; kill stands on lead quality). `/settings` got example procedures per group + a
  pay/charge→% calculator for Dr. Recalde (percentage model needs no unit counts — product cost scales
  with revenue). **LTV IS captured** — the engine sums ALL post-acquisition visits across every service,
  so a Botox ad gets credit for whatever those patients buy later (Josh's core hope: answered YES).
- **✅ INSTAGRAM organic pull LIVE 2026-07-08.** `/api/instagram` pulls @medglo.oc (IG id
  17841429678372109) post reach/saves/shares/engagement → `instagram_posts` table; daily cron
  7:20am PT (`instagram-pull.yml`). Setup done end-to-end: added the "Manage messaging & content on
  Instagram" use case + `instagram_basic`/`instagram_manage_insights` to the MedGlo Analytics app;
  Josh generated a **never-expiring System User token** (medglo-analytics SU) → Vercel `IG_ACCESS_TOKEN`
  (separate from the ads `META_ACCESS_TOKEN`, which was verified still working). NOTE: that token also
  carries ads_management + full Page/IG/ad-account access → it's the future agent's key too (treat as
  sensitive; revoke from the SU screen if leaked). Insight metrics use `views` (impressions/plays were
  deprecated). **First finding: a June-22 reel ("be kind to all patients") hit 73k reach / 2,936 shares
  — a viral organic post worth boosting as an ad.** Warm/human reels >> informational ones.
- **META-AD AGENT — GREENLIT 2026-07-08, Josh spinning up its own session ("Medglo - Meta Agent") via Chief.**
  Full kickoff prompt handed to Chief (Scorecard session wrote it). **DECIDED design (Josh's call):**
  agent **ACTS autonomously** (adjusts budgets, toggles ads on/off, tests concepts) — NOT advisor-first —
  and **catalogs every change to a dashboard change-log with EXACT prior-state + one-click Revert** (revert
  via Meta API so Josh never digs through Meta; Andrea sees changes too). **Safeguards = the money protection
  (revert does NOT refund spent $):** hard caps (weekly ceiling/circuit-breaker, per-ad daily max, ±20%/wk
  change cap), anti-"$1k-on-a-dud" auto-kill (respect the 11-day booking lag — pause after ~2-3wk/$150-200
  spent w/ 0 booked), learning-phase spend cap + kill-by date, global kill switch, no thrashing. Optimize on
  **cost per booked/showed + true-profit/cross-sell, NEVER CPL or raw ROAS.** Key = the medglo-analytics SU
  token (ads_management; give agent its own env var). Existing-ad toggle/budget = autonomous; NEW creative
  goes through Andrea + `message-playbook.md`. Reuses the scorecard budget-call/actions engine as its brain.
  **Needs Josh (agent session will ask):** hard $ caps, may-it-create-new-ads-or-only-toggle, creative-brief
  turnaround. **Data-source plan (NOTES.md):** class A = performance (have; ADD creative-level ad metrics
  [queued — task chip], IG organic [LIVE], Google Business Profile); class B = trend/creative-intel (Meta Ad
  Library, Google Trends, own reviews/GHL, TikTok) for GENERATING creative, human-gated. Ahrefs = own-site SEO
  not trend detection; Apify private-FB-group scraping = AVOID (ToS/legal/noise), public content only.
- **✅ CREATIVE-METRICS PULL LIVE 2026-07-08.** `/api/creatives` joins Marketing API /ads (copy, headline,
  format, thumbnail, CTA) + /insights (hook/hold/CTR/video-retention/quality rankings/leads) per ad →
  `creative_metrics` table (87 ads loaded); daily cron 7:10am PT. Uses existing ads_read META_ACCESS_TOKEN.
  **All 3 Meta-Agent data streams now live: ad performance + IG organic + creative metrics.**
  **Early creative findings:** doctor-wedge STATIC ads win CTR (Skip-the-Chains 3.1%, No-Pressure 2.9% —
  playbook copy works); reels hook ~95% (autoplay) but HOLD poorly (3.6–13.8%; warm/human "We used our Pico"
  held best 13.8%, informational reels <5%) → reels need a stronger middle/payoff. Caveats: quality_ranking
  UNKNOWN until an ad clears Meta's impression threshold; dynamic-creative ads capture only the first body variation.
- **✅ scorecard_goals table created (Josh ran the SQL 2026-07-08)** — goals now editable at
  /scorecard/goals; still all "draft" (setByJosh empty) until Josh sets real numbers.
- **Needs Josh:** (1) confirm/adjust the draft goals + road stages at /scorecard/goals (esp. the
  revenue goal = Stage 1); (2) real overhead/COGS + does $30k include Dr. R's pay?; (3) to activate
  Instagram: mint a Meta token with the IG scopes (NOTES.md); (4) the Botox per-unit margin question.
- **Caveats:** ⚠️ **UPDATE — Stream A's "don't-trust-revenue" verdict is RESOLVED as of 2026-07-08:**
  the invoice engine was rewritten + all history rebuilt, coverage is now 97–100% every month, so
  revenue/ROAS are trustworthy and the "revenue is a floor" coverage banner auto-clears (it only
  shows below ~90%). The scorecard's live coverage check still guards correctly if capture ever dips. The
  med-spa/primary-care split counts the **"Medical Consultation" appointment type in CalystaPro** —
  front desk must book PC visits under that type or they count as med-spa. Google review count has
  no API. A custom warning banner can be set at /scorecard/goals (no redeploy) once the SQL is run.

## STREAM F — Meta Agent (daily ad-optimization agent)   ← session "Medglo - Meta Agent"
- **✅ BUILT + DEPLOYED 2026-07-08 (commit 4b08897) — LIVE IN DRY-RUN MODE.** All 5 build stages
  shipped: caps/settings + change-log with exact-prior-state + one-click Revert (`/agent` page,
  Andrea's viewer login sees it read-only) · Meta write layer (pause/activate/budget, verify-after-
  write, revert = re-apply prior state) · daily decision engine extending the scorecard LADDER
  (auto-kill matured 0-booked ads, learning-phase caps + kill-by, ladder raise/cut on the cheapest/
  most-expensive booker, reactivate proven winners; ±20%/wk, no-thrash, max-changes/run, weekly
  circuit breaker, cost/booked auto-halt, kill switch) · learning loop (expected→actual→verdict
  after 14d) · creative-brief loop (viral-IG + fatigued-winner briefs → Andrea, Josh approves at
  /agent; NEVER auto-launched). Cron: `agent-run.yml` daily 10am PT. Raw detail: `MedGlo-marketing/NOTES.md`.
- **FIRST RUN (dry, live data, 2026-07-08):** scorecard says RAISE ($139/booked, suggest $830/wk);
  agent would (1) auto-kill "Girl Math PICO Summer - IG Reel" (running, ≥$175/90d, 0 booked),
  (2) raise budget on "Tattoo_Removal_Laser_Spanish_V1" (cheapest proven booker), (3) reactivate
  "$1,680 Mistake — Refresh #1" (proven winner, currently off). NO changes were made.
- **AUTHORIZATION (Josh, written, 2026-07-08):** the agent ACTS autonomously (no advisor phase) on
  toggles/budgets of EXISTING ads — **valid only once Josh's hard $ caps are set and recorded in this
  block.** Until the cap numbers are written here, the agent makes NO live changes (enforced in code:
  dry-run until "caps confirmed" is ticked at /agent). New patient-facing creative is NEVER
  auto-launched: brief → Andrea → playbook QA → Josh reviews.
- **CAPS: ⏳ AWAITING JOSH (asked 2026-07-08 in the Meta Agent session).** To set: weekly ceiling
  (circuit breaker; suggest $850 ≈ scorecard's $830) · per-ad daily max (suggest $40) · auto-kill
  (defaults: ≥17 days old + ≥$175/90d + 0 booked → pause) · learning-phase test budget (default
  $75/wk; kill-by = the auto-kill date) · new-test-ads autonomously? (default NO — toggle/budget
  only) · creative-brief turnaround. Once Josh answers → record numbers HERE + enter at /agent +
  tick "caps confirmed" → agent goes live. All defaults editable at /agent anytime.
- **TO GO LIVE (3 steps, ~5 min):** (1) paste `supabase/RUN_THIS_IN_SUPABASE.sql` in the Supabase
  SQL editor (also creates the still-missing `creative_metrics` table — its daily cron has been
  failing since it shipped); (2) add Vercel env `AGENT_META_TOKEN` = the medglo-analytics System
  User token (same value as IG_ACCESS_TOKEN; the agent's own key — writes use ONLY this); (3) set
  caps at marketing.med-glo.com/agent + tick confirm. Until then: daily dry-runs log what it WOULD do.
- **Note:** the creative-level ad-metrics pull (`/api/creatives` + cron) was already built by the
  scorecard session — only its table SQL is missing (step 1 covers it). It feeds the agent's
  fatigue briefs; the budget/on-off logic works without it.

---

## NEEDS JOSH (cross-cutting)
- The concrete **GOAL number**.
- **Fix the website:** remove **CareCredit** everywhere — you only accept **Cherry** (Dr. Recalde flagged
  this in April; site still lists CareCredit). Already corrected in the bot KB.
- Ops fix until the bot is live: **15-min reply SLA** on lead questions + a **7–8pm inbox sweep** (leads
  text evenings; replies currently go out ~11am next day — the 15.5h lag is the #1 booking leak).

## RECENTLY DONE (2026-07-08, Dashboard Data Audit session)
- Full pipeline audit (all steps verified to source) + invoice-engine rewrite + overnight
  historical backfill of every patient's paid-invoice history. Revenue/ROAS now real.
  Details: Stream A above + `MedGlo-marketing/NOTES.md`.

## RECENTLY DONE (this session, 2026-07-06/07)
- Ad audit + 4 ad kills executed; Supabase tables created + follow-up sync run; dashboard upgraded
  (follow-up health, $/booked, coverage banner).
- New ad creative + production guide written; GHL bot KB built (site crawl + team-WhatsApp mining).
- Primary-care funnel approved + website PR #103 merged.
- Website rebuilt Mar 2026 (`MedGlo-website/MEDGLO_BLUEPRINT.md`); VoC study → `Competition/message-playbook.md` (voice LAW).
