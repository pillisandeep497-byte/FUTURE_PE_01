# PROMPT 06 — Anti-Generic QA Scorecard (the editing prompt)

This is the prompt that most interns skip and most reviewers notice. Run it on your own AI output before submitting — and keep the scored result in the repo.

---

## PART A — Banned-phrase scan (paste your output, run this)

```
You are a ruthless copy editor. Scan the text below for AI-generic language.

FLAG every instance of these, and any close variant:
unlock, unleash, elevate, embark, journey, passion, passionate, dedicated team,
state-of-the-art, cutting-edge, world-class, top-notch, best-in-class, premier,
one-stop shop, seamless, hassle-free, tailored, bespoke, curated, holistic,
indulge, pamper, rejuvenate, revitalise, transform (unless a real transformation
with a number), game-changer, look no further, nestled, in today's world,
we pride ourselves, customer satisfaction is our priority, quality is our priority,
wide range of, all your needs, contact us for more information, click here,
learn more, get in touch, we'd love to hear from you, at competitive prices.

ALSO FLAG these structural problems:
1. Triads of adjectives ("professional, friendly and affordable") — cut to one.
2. Sentences starting with a participle ("Committed to excellence, we...")
3. Any paragraph longer than 4 sentences.
4. Any sentence that would remain true if you swapped the business name for a
   competitor's name. Mark these as GENERIC — they are the worst kind.
5. Any claim without a source (number, brand, name, review, process).
6. Any superlative without proof.
7. More than one exclamation mark per page.
8. Any "we" sentence that should be a "you" sentence.

OUTPUT: a table with | Line | Problem | Severity (High/Med/Low) | Rewrite |
Then give a revised version of the whole text with every High-severity issue fixed
and Medium/Low issues fixed where the sentence can stay short.
```

---

## PART B — The 25-point conversion scorecard

Score your final copy honestly. Anything under 18 means "do not send to client yet".

| # | Check | Weight | Score (0–2) |
|---|---|---|---|
| 1 | H1 states the outcome in ≤10 words, understandable in 5 seconds | x2 | |
| 2 | Sub-headline names who it's for and the main benefit | x1 | |
| 3 | Intro answers what/who/why-different in the first 2 sentences | x1 | |
| 4 | At least 6 concrete specific details (numbers, brands, names, prices) in body copy | x2 | |
| 5 | Top 3 objections from the brief are answered somewhere on the page | x2 | |
| 6 | Price or price range appears (or the reason it can't) | x1 | |
| 7 | Every CTA is verb + object + outcome + timeframe | x2 | |
| 8 | A risk-reversal or guarantee line exists | x1 | |
| 9 | Real urgency only; no fabricated scarcity | x2 | |
| 10 | Local proof: area, landmark, or travel line present | x1 | |
| 11 | Proof points are verifiable from the brief (no invented reviews/credentials) | x2 | |
| 12 | Reading level ≈ class 8–10; avg sentence ≤ 18 words | x1 | |
| 13 | Mobile-scan test: bold labels, bullets, short paragraphs, no wall of text | x1 | |
| 14 | Zero banned words | x1 | |
| 15 | Passes the SWAP TEST: no line works verbatim on a competitor's site | x2 | |
| 16 | Page ends with one clear next step | x1 | |
| 17 | Consistent tense, person, and tone throughout | x1 | |
| 18 | FAQ uses real customer language, not marketing language | x1 | |
| 19 | One screenshot-worthy line (a line a customer would send to a friend) | x1 | |
| 20 | SEO title/meta within character limits, keyword first | x1 | |
| 21 | No legal or compliance risk (medical claims, guarantees, price promises) | x2 | |
| 22 | Tone matches the brief's must-sound-like words | x2 | |
| 23 | Client's own words/brands are used, not your substitutes | x1 | |
| 24 | Fits the word budget for the page type (homepage ≤ 850 words body) | x1 | |
| 25 | You would publish this under your own name | x2 | |

**Total possible: 36 points.** Interpretation:
- 32–36 → portfolio-ready, send to client.
- 26–31 → good, tighten specifics and CTAs.
- 18–25 → generic risk. Rerun PROMPT 01 with more brief detail.
- <18 → the brief is too thin. Go back to PROMPT 00 and gather real detail.

---

## PART C — The 3 tests every local-business copywriter should run

**1. The Swap Test.** Replace the business name with the strongest competitor's. If nothing breaks, the copy is generic. Real copy breaks immediately (prices, names, processes, area).

**2. The Read-Aloud Test.** Read it out. If you would be embarrassed to say the sentence to a customer's face, cut it. "We pride ourselves on delivering holistic beauty solutions" — nobody has ever said that out loud.

**3. The 5-Second Test.** Show only the H1 + sub-headline to someone for 5 seconds. Ask: what does this business do, who is it for, and what should you do next? If they can't answer all three, rewrite the hero.

---

## PART D — Human pass checklist (do this manually before submitting)

- [ ] Read the whole page out loud once. Cut every sentence you stumble on.
- [ ] Add at least 3 details the AI could not have known (from your site visit: the owner's name, the chair count, the chai they offer waiting customers, the fact they keep Tuesday afternoons free for walk-ins).
- [ ] Replace any [NEEDS CLIENT INPUT] / [CONFIRM] flags with real answers OR leave them visibly flagged for the client (this is a feature, not a bug — it shows diligence).
- [ ] Verify every price, number and credential against the brief one more time.
- [ ] Delete all `> Rationale:` notes from the client-facing version; keep them in the repo version as a separate file.
- [ ] Spell-check names of brands (L'Oréal Professionnel, not "Loreal Professional").
