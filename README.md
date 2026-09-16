# AI Website Copy Generator for Local Businesses

**A structured prompt system that produces conversion-focused website copy for local businesses — homepage, services page, CTAs, and local SEO — in one repeatable workflow.**

Built for **Future Interns — Prompt Engineering Task 1 (2026)**.

**Author:** Pilli Sandeep · **Contact:** WhatsApp +91 91002 12761
**Repository:** [github.com/pillisandeep497-byte/ai-website-copy-generator](https://github.com/pillisandeep497-byte/ai-website-copy-generator)

---

## What problem this solves

Local businesses — salons, cafes, clinics, coaching institutes, agencies — lose customers because their website copy is unclear, generic, and never asks for the sale. Professional copywriters cost more than a small business wants to spend, and owners don't know what to write.

This repo is a **reusable prompt system**: fill one intake brief, run seven prompts, and get copy that is specific, honest, and ready to publish. It is designed the way an agency works — briefing, generation, tone adaptation, QA, client delivery.

**The core idea:** most "AI copy" fails because the input is generic. This system spends its effort on *input quality* (a 12-question intake brief), *structure* (a fixed 11-section page skeleton), and *guardrails* (a banned-phrase list, a specificity quota, and a swap test) — so the output can't be generic even if you want it to be.

---

## The chosen business (client run)

**Glow Studio by Sanjana** — Beauty salon & bridal studio
1st Floor, above Sri Sai Bakery, MVP Colony Main Road, Sector 4, Visakhapatnam, Andhra Pradesh
7 years in business · Hair, keratin, colour and bridal makeup · 4 chairs

**Problem addressed:** the studio's copy risked being one of dozens of identical "best salon in Visakhapatnam" pages. The copy in this repo:
- Leads with outcomes instead of adjectives ("Hair that behaves every morning")
- Puts **prices in text** where Google can read them — the highest-value SEO gap at most local businesses
- Publishes the studio's **honest disqualifiers** ("if your hair can't take keratin, we'll say no") because that is what actually converts a suspicious first-time visitor
- Makes every claim verifiable with a number, a brand name, a policy, or a place

> ⚠️ **Integrity note:** this client run is a *representative* Visakhapatnam salon built as a working demonstration. Every price, count and testimonial is marked `*(verify)*` or `[REPLACE WITH REAL REVIEW]`. When running this system for a real paying client, replace those with confirmed facts. Nothing in the copy deck is presented as verified data.

📄 Full brief: [`client-runs/01-glow-studio-vizag/brief.md`](client-runs/01-glow-studio-vizag/brief.md)

---

## The prompt logic (how the system works)

Every prompt follows the same eight-part skeleton. If you only read one thing in this repo, read this.

```
ROL  →  ROLE            You are a conversion copywriter who has stood in the shop
DNA  →  CLIENT DNA      Variables from the intake brief — the single source of truth
TASK →  TASK            Exact deliverable, section by section, with word budgets
CONS →  HARD CONSTRAINTS Specificity quota, sentence length, mobile scan rules
BAN  →  BANNED LIST     30+ AI-cliché phrases + the "swap test" rule
FMT  →  OUTPUT FORMAT   Markdown schema that drops into Framer / Lovable / WordPress
BAR  →  QUALITY BAR     5 self-checks the model must pass before answering
CHK  →  SELF-CHECK      Scored 1–5 across 5 dimensions, printed with the output
```

**Five design decisions that make the output good:**

| Decision | Why it matters |
|---|---|
| **One intake brief feeds every prompt** | Kills invented facts. The model is told: *never invent a price, award or testimonial; write `[NEEDS CLIENT INPUT]` instead.* |
| **A banned-phrase list, enforced** | Without it, every business gets "unlock", "elevate", "one-stop shop". The list makes genericness a rule violation, not a taste question. |
| **The swap test** | *If a competitor could paste this line on their site unchanged, it's generic — delete it.* This single rule produces most of the specificity in the final copy. |
| **Specificity quota** | One concrete detail (number, brand, price, timeframe, named place) per ~25 words. Measurable, so it can be scored. |
| **Objections before features** | The prompt requires the top 3 customer fears to be answered on the page. Fear removal converts better than feature lists for local services. |

**The tone adapter is what makes it reusable.** Rather than swapping nouns (`salon` → `clinic`), `prompts/04` changes the three things that actually define a voice: **sentence rhythm, proof type, and urgency mechanism** — with five profiles (friendly, professional, confident-simple, premium-calm, warm-clinical) and an explicit ban on light synonym-swaps.

📄 See the proof: [`client-runs/adaptability-proof.md`](client-runs/adaptability-proof.md) — same prompt, five business types, five genuinely different voices.

---

## Tools used

| Tool | Role in this project |
|---|---|
| **Claude** | Primary long-form generation — homepage, services page, CTA blocks. Best banned-word compliance and schema adherence. |
| **ChatGPT** | Tone adaptation across business types, and the anti-generic QA scan. |
| **Gemini** | Local SEO layer — meta titles, keyword map, FAQ, answer-engine snippets. |
| **Lovable / Framer AI** | Where the copy is intended to be published. The output format is deliberately section-based markdown so it converts cleanly into web-builder sections. |
| **Canva / Chrome** | Screenshots for the LinkedIn writeup and the repo preview. |

Practical workflow: **Claude for the page copy → Gemini for SEO → ChatGPT for QA.** One brief file, pasted identically into each, so all three models work from identical facts. Full comparison in [`client-runs/01-glow-studio-vizag/prompt-log.md`](client-runs/01-glow-studio-vizag/prompt-log.md).

---

## Repository structure

```
.
├── prompts/                                  ← THE SYSTEM (the real deliverable)
│   ├── 00-client-intake-brief.md             ← 12-question intake + variable map
│   ├── 01-homepage-copy.md                   ← hero, problem, differentiators, FAQ, closing
│   ├── 02-services-page-copy.md              ← service blocks, comparison table, packages
│   ├── 03-cta-trust-blocks.md                ← 10 CTA patterns + placement map
│   ├── 04-tone-and-language-adapter.md       ← 5 tone profiles + language-mix rules
│   ├── 05-seo-meta-faq-local.md              ← meta, keywords, schema, answer snippets
│   └── 06-editorial-qa-scorecard.md          ← banned-phrase scan + 25-point scorecard
│
├── client-runs/
│   ├── 01-glow-studio-vizag/                 ← FULL CLIENT BUILD-OUT
│   │   ├── brief.md                          ← filled intake brief
│   │   ├── homepage.md                       ← generated + annotated (with rationale)
│   │   ├── services.md                       ← 9 service blocks, packages, FAQ
│   │   ├── ctas.md                           ← 10 CTA blocks + placement map
│   │   ├── seo-meta-faq.md                   ← meta tags, keyword map, schema, snippets
│   │   ├── qa-scorecard.md                   ← scored 35/36 + editing log
│   │   ├── prompt-log.md                     ← which prompt made what, model comparison
│   │   └── final-copy.md                     ← ⭐ the client-facing deliverable
│   └── adaptability-proof.md                 ← one prompt, 5 business types, 5 voices
│
├── preview/
│   └── index.html                            ← the copy rendered as a real homepage (open in a browser)
│
└── docs/
    ├── submission-checklist.md               ← every task requirement → the file that satisfies it
    ├── linkedin-post.md                      ← ready-to-post writeups + screenshot list
    ├── client-outreach-whatsapp-email.md     ← the "Learn & Earn" pitch + review scripts
    └── tools-and-workflow.md                 ← tool-by-tool workflow notes
```

---

## How to reuse this for a different client (5 steps, ~2 hours)

1. **Intake** — run `prompts/00` with the business owner (20 min on a call, or use it as a site-visit script). Fill `brief.md`.
2. **Homepage** — paste the brief + `prompts/01`. Pick one of three H1 angles using the reasoning given.
3. **Sub-pages** — run `prompts/02` (services) and `prompts/03` (CTAs).
4. **Adapt or extend** — different business type? Run `prompts/04`. Need search traffic? Run `prompts/05`.
5. **QA** — run `prompts/06`. Fix every High-severity flag. Add 3 facts only a local person could know. Deliver.

**What stays constant:** the skeleton, the constraints, the banned list, the specificity quota.
**What changes:** the brief, the tone profile, the proof type, the urgency mechanism.

That is the whole system — and it's why it can be sold repeatedly.

---

## Results

| Metric | Result |
|---|---|
| Client pages delivered | 4 (homepage, services, bridal, contact) + meta tags |
| Services written | 10 service blocks + 3 packages |
| CTA blocks | 10 (booking, trust, risk reversal, location, time urgency, capacity, soft, post-enquiry, closing, micro) |
| QA score | **35 / 36** on the 25-point weighted scorecard |
| Banned phrases in final copy | **0** (10 flagged in the raw draft, all fixed — see the editing log) |
| Specific concrete details | 40+ (every price, brand, policy and timeline traceable to the brief) |
| Lines that fail the swap test | 0 |
| Businesses the prompt system has been proven on | 5 (salon, cafe, clinic, coaching, freelancer) |

---

## Honest limitations (what the system does not do)

- **It cannot invent proof.** Where the brief has no reviews or numbers, the copy carries a visible flag instead of a fake claim. This is deliberate: fabricated testimonials and credentials are a legal and reputational risk for the client.
- **It still needs a human pass.** The AI gets ~80% of the way; the last 20% — local landmarks, the owner's real language, the details only a site visit reveals — is what makes it good. `prompts/06` Part D is that checklist.
- **Character counts in meta tags must be verified manually.** All three models are approximate here.
- **It is not a website.** It produces copy in a web-builder-friendly schema. Layout, images and technical SEO still need doing (Lovable or Framer handles that part).

---

## License & attribution

MIT. Prompt system designed by Pilli Sandeep for the Future Interns Prompt Engineering Internship, 2026. The "Glow Studio by Sanjana" client profile is a representative demonstration, not a verified business record.
