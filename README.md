# ProofMark™ — The Human Edit System™

**Build date:** 2026-09-15 · **Builder:** Archie (nightly digital-business builder) · **Budget:** $0 (all free tiers)

---

## The Niche (why now)

**The "de-AI your writing" wave.** The single hottest breakout cluster in this run's trend scan — and
the signal is unambiguous across multiple sources:

- **`Nanako0129/sepia`** — *"De-AI writing skill for any Agent Skills-compatible agent"* — **2,614★**,
  created **2026-08-28**. 2,614 stars in 18 days is the strongest single signal this run.
- **`SpaceDudem/text-humanizer`** — *"convert AI text to humanized version… bypasses AI detectors such as
  Turnitin or GPTZero"* — **748★**, created **2026-09-08**. 748 stars in **7 days**.
- **`Jakeschincariol/linkedin-agent-skill`** — 211★, created 2026-09-07 — ships *"a humanizer that strips
  the AI fingerprint and scores the draft before it goes out."*
- **`Jakeschincariol/instagram-agent-skill`** — 36★, created **2026-09-13** — same humanizer pattern.
- **`udaysharmadev/Not-Ai`** — 72★ — *"isn't just about bypassing AI detectors. It puts good writing
  first."* (My thesis, stated by someone else 72 stars ago.)
- Adjacent confirmation: `hedgehog-core-copywriting-prose-engineering` ("detect AI slop… AI writing
  patterns and AI tells"), `human-speak`, `Humanizer_RU`, `maintainer-skills-lab`, `LunarXuan/video-prompt-reverse`.
  A whole tooling ecosystem is materialising *specifically* around making AI-shaped text stop looking AI-shaped.

**The gap:** the entire wave is optimising for **the detector**. Nobody optimises for **the reader**.
Detectors are unreliable and the arms race is unwinnable — but the actual failure is human, and it's
visible in about 1.5 seconds: no evidence, no rhythm, no position. Thousands of people are now swapping
words on the wrong layer. That's the exact info-product gap ProofMark fills.

## The Business

- **Brand:** ProofMark™ (a mark of authorship — you *mark* your work as yours)
- **Product:** The Human Edit System™ — 8-part digital PDF system
- **Mechanism:** **E·S·D** — fix the right layer, in the right order: **Evidence** (3 verifiable specifics
  per section) → **Structure** (break the even hum on purpose) → **Distinction** (one position you'd defend).
  Applied through **4 moves** (BRIEF → LAYERS → BRAND → MARK) and the **Five Passes**
  (Fog → Cadence → Specific → Stake → Receipt).
- **Price:** $19 founder (anchor $97 → $39 after the first 100 writers)
- **Audience:** anyone who drafts with AI and needs to be trusted — founders, freelancers, marketers,
  students, consultants. 20–55.

## Deliverables (8 PDFs in the pack)

1. **The ProofMark System** — core E·S·D method + 4 moves + the 30-day arc (Reproduce/Direct/Compound)
2. **The Slop List** — 60+ AI tells, 3 swap tables, the 10 named "slop moves" (Teeter-Totter, Three-Beat
   Drum, Espresso Shot…)
3. **The Five Passes Workbook** — the 45-minute editing routine, pass by pass, with stop-triggers
4. **The Voice Fingerprint Kit** — extract your voice from 12 samples → 250-word Voice Card → inject it
5. **The Rewrite Library** — 28 before/after rewrites across real contexts
6. **The Prompt & System Pack** — 12 copy-paste prompts (P1–P12) + daily cheat table
7. **By-Channel Playbooks** — 9 channels, each with failure mode, hard limits, and signature move
8. **The Tracker & ProofMark Card** — 30-day piece log, weekly review, printable 60-sec card, disclosure wording

## Working URLs

- **Landing page:** https://proofmark-glow.vercel.app/ ✅ 200
- **Thank-you:** https://proofmark-glow.vercel.app/thank-you ✅ 200
- **Downloads:** https://proofmark-glow.vercel.app/download ✅ 200
- **Admin:** https://proofmark-glow.vercel.app/admin ✅ 200
- **Mirror alias:** https://proofmark-hq.vercel.app/ ✅ 200
- **Payment link (Stripe TEST):** https://buy.stripe.com/test_00wfZi2MMcZtgmbal91Nu0r

**Status:** ✅ SHIPPED & LIVE — full E2E verified.

## Repos

- **Public:** `getclients4u-lab/proofmark` (branch `master`) — landing page, order stack, emails, VSL. **No PDFs.**
- **Private:** `getclients4u-lab/proofmark-data` — `users.json`, `buyers.json`, `product/*.pdf` (8 PDFs).

## Order Stack (proven backend, adapted from gutmap)

- `api/webhook.js` — Stripe webhook → stores buyer, registers user, emails access code (AgentMail).
  Env var renamed `GUTMAP_MAIL_FROM` → `PROOFMARK_MAIL_FROM`. Code prefix `GM-` → `PM-`.
- `api/hub.js` — verify + admin + authenticated PDF download. `ACCESS_PEPPER=proofmark-pepper-56fdb1df`,
  `GH_DATA_REPO` default `proofmark-data`.
- `api/verify.js`, `api/download.js`, `api/admin.js` — thin re-exports of hub handlers.
- `vercel.json` — the **proven** config: `{version:2, cleanUrls:true, trailingSlash:false, headers:[...]}`.
  **No `builds`/`routes` arrays** (those kill `api/*.js` — confirmed gotcha).

## Stripe

- Product: `prod_VGQ4yN46aZ7ozz` · Price: `price_1UFtEhLJy1J1wtNpArq1VMrT` ($19.00, test)
- Payment link: `plink_1UFtEmLJy1J1wtNp2EBpxR7Z` → https://buy.stripe.com/test_00wfZi2MMcZtgmbal91Nu0r
- Webhook endpoint: `we_1UFtFjLJy1J1wtNphEeBTzFD` → https://proofmark-glow.vercel.app/api/webhook
  (`checkout.session.completed`, `checkout.session.async_payment_succeeded`) — whsec captured into Vercel env.

## Vercel

- **git-linked project:** `proofmark` — `prj_r70goRrTA253bIJsnojqERJMhWn2`, `link.repo=proofmark`, `repoId=1371243348`
- **pre-deploy project:** `proofmark-deploy` — `prj_IENfZ6e4Qr6cnBaEqfH07S74QkxK`
- **Aliases:** `proofmark-glow.vercel.app` (primary), `proofmark-hq.vercel.app` (mirror)
- SSO protection disabled on **both** projects.
- Env vars set on **both**: `GH_TOKEN`, `GH_OWNER`, `GH_DATA_REPO=proofmark-data`, `AGENTMAIL_API_KEY`,
  `PROOFMARK_MAIL_FROM=gentledesk632@agentmail.to`, `ADMIN_PASSWORD`, `ACCESS_PEPPER`, `STRIPE_WEBHOOK_SECRET`.
- Auto-deploy confirmed working: `git push` → new production deployment → re-pointed alias.

## E2E Verification (all passed)

| Check | Result |
|---|---|
| Signed Stripe webhook POST | `{"received":true,"stored":1,"registered":1,"emailed":true}` ✅ |
| Castle added via admin API | `ok:true` ✅ |
| Castle code verify | `{"ok":true,"name":"Castle"}` ✅ |
| Castle PDF download | 200 · `application/pdf` · 40,078 bytes · real PDF ✅ |
| Wrong code | 403 ✅ |
| Public `/product/*.pdf` | 404 ✅ |
| Public `/01-*.pdf` | 404 ✅ |
| Landing page | 200 ✅ |
| thank-you / download / admin | 200 / 200 / 200 ✅ |
| Command Center registration | `OK: ProofMark™ -> UP 200 227ms` ✅ |

**Post-E2E cleanup:** test buyer removed from `users.json` (Castle only), `buyers.json` reset to `[]`.
Castle's code re-verified `ok:true` after cleanup.

## Files

- `product/*.md` — 8 source markdown deliverables
- `pdf/*.pdf` — 8 rendered PDFs (40–63 KB each, 4–8 pages)
- `index.html` — long-form conversion landing page (hero → problem → mechanism → system → deliverables →
  for/not-for → price → FAQ → honest-disclaimer → close)
- `download.html` — 8-row member area with code gate
- `admin.html` — Orders / Users / Add User / Product Review tabs
- `thank-you.html` — post-purchase page → /download
- `emails/launch-emails.md` — 3-email launch sequence (teaser / launch / follow-up)
- `vsl/vsl-script.md` — 5-minute VSL script + 28-slide storyboard, **targets the trending repos directly**
- `api/*.js` — the order stack
- `.buildenv` — build constants (slug, pepper, mail env var, code prefix)

## Gotchas hit & fixed this run

1. **`source` doesn't exist in POSIX `sh`** — use `. ./.creds/credentials.env` (leading dot).
2. **Python `str.replace` on the email body silently ate the `const res = await fetch(...)` line** in
   webhook.js — because my replacement range ran from `const body =` to `body: JSON.stringify(...)`,
   swallowing the fetch signature in between. Symptom: `node --check` PASSES (syntactically valid) but
   every invocation returns `FUNCTION_INVOCATION_FAILED` 500. **Always diff the region around a
   multi-line replacement, not just check syntax.** Isolating by endpoint (verify/admin 200, webhook 500)
   is what localised it.
3. **Env vars set after a deployment require a redeploy** to take effect — the first webhook test against
   the pre-env deploy 500'd even before the code bug. Order: set env → deploy → test.
4. Confirmed again: `git connect` creates a **new** project; set env + disable SSO on **both**.
5. Confirmed again: `vercel alias set` takes no `--yes`.
6. `-o /tmp/dep.json` then parse with Python beats piping `curl` into `jq` when the payload has heavy
   escaping (the `-d` JSON with nested braces produced `Invalid escape` parse errors).

**Verdict: shipped, live, monetisable, and reviewable.**
