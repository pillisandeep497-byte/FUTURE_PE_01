# PROMPT 02 — Services Page Content Generator

Turns the brief's service list into pages that sell. Output for Glow Studio: `client-runs/01-glow-studio-vizag/services.md`.

---

## The prompt

```
# ROLE
You are a conversion copywriter for local service businesses. You know that a
services page is not a price list — it is a set of answers to "will this work for
me, what exactly do I get, and what will it cost me in money and time?"

# CLIENT DNA
<PASTE THE FILLED CLIENT BRIEF HERE>

# TASK
Write the complete Services Page for {{BUSINESS_NAME}} ({{CATEGORY}}) in {{CITY}}.

A) PAGE HEADER
- H1 (max 12 words) that names the category + the area, not a slogan.
- Intro paragraph, 40–60 words, that explains how their services are organised
  (by result, by budget, or by occasion) so the visitor knows where to click.

B) SERVICE BLOCKS — one block per service in the brief (minimum 6). Use this
exact schema:

### {{SERVICE_NAME}}
**One-line promise:** (result-focused, max 12 words, no adjectives like "premium")
**Best for:** (specific person/situation — "women whose hair has gone frizzy after
monsoon", not "anyone who wants to look good")
**What's included:** 4–6 bullets. Each bullet names a product, technique, tool or
timeframe. No bullet may be generic ("professional consultation" is banned unless
you say what is decided in it).
**How long it takes:** (chair time + how long the result lasts, honestly)
**Price:** from the brief, with a plain-English note on what changes the price
(hair length, product range, add-ons)
**Before you book:** one honest line about prep, patch tests, or who this is NOT
right for. This builds more trust than any adjective.
**CTA:** action + outcome + timeframe (e.g. "Send a hair photo on WhatsApp — get an
exact quote in 15 minutes.")

C) WHICH SERVICE SHOULD I PICK? — A 3-row comparison table for the three most
confused-about services (e.g. keratin vs smoothening vs botox), with: Goal |
Best for | Lasts | Rough price. Plus one sentence of "if you're still unsure, here
is how we decide".

D) HOW A VISIT WORKS — 4 steps, with honest timings and what the customer is told
at each step.

E) WHY {{BUSINESS_NAME}} — 5 proof-driven reasons. Each: bold 4-word label +
1–2 sentences. Must include at least one number and one named brand/product/
credential per reason.

F) PACKAGES / BUNDLES — 3 packages: Good, Better, Best. Name them using the
customer's outcome, not "Silver/Gold/Platinum" (banned). For each: who it's for,
what's included, what it costs, and one saving/certainty line.

G) SERVICE FAQ — 6 blunt questions specific to these services (not brand-level
questions). Include price, pain, damage risk, and aftercare.

# HARD CONSTRAINTS
- Never write "we offer". Start with the customer's result or the service name.
- Every service block must name at least one product brand or technique from the brief.
- Keep bullets to max 12 words. Bullets are scanned, not read.
- If the brief lacks a price, print [PRICE TO CONFIRM] rather than inventing one.
- Do not use the same sentence structure in two consecutive service blocks.
- Order services by what the business most wants to sell, and say why in a note.

# BANNED
premium, luxurious, rejuvenate, revitalise, pamper, indulge, glow-up (unless the
brand name says it), bespoke, tailored, state-of-the-art, world-class, one-stop shop,
"wide range of services", "solutions for all your needs", "unleash your beauty",
"because you deserve it", "treat yourself".

# OUTPUT FORMAT
Markdown, publish-ready. Add `> Rationale:` lines under each block for my internal
review. Add a final section "SEO NOTES" listing the 5 keyword phrases each service
block should target (local intent: "keratin treatment MVP Colony Visakhapatnam price").

# SELF-CHECK
1. Does each service block answer: what do I get, how long, how much, is it safe for me?
2. Are two service blocks written so differently that a reader doesn't get bored?
3. Would a customer be able to choose without calling you first? If yes, good.
4. Zero banned words?
End with "--- SELF-CHECK PASSED ---" and scores for Clarity, Specificity,
Trust-building, Scannability, Banned-word compliance (1–5 each).
```

---

## Local-business service-page patterns (steal these)

1. **The honest disqualifier.** "Not right for you if your hair has been lightened twice in the last month — we'll suggest a repair plan instead." Nothing sells like the truth.
2. **The cost-transparency block.** "Why prices vary" beats "contact us for pricing" in every A/B test a local business will ever run.
3. **The three-way comparison table.** Customers compare keratin vs smoothening vs botox and pick nothing. A table converts indecision.
4. **Outcome names for packages.** "Wedding Week Ready" (₹X), "Monthly Hair Care" (₹Y), "Bridal + 3 Guests" (₹Z) — not Silver/Gold.
5. **The "what happens after" line.** Aftercare instructions inside the service block reduce complaints and increase rebookings.
