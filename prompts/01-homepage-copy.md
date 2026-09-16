# PROMPT 01 — Homepage Copy Generator

Use after the Client Brief is filled. Works in ChatGPT (GPT-5 class), Claude, Gemini. Tested output for Glow Studio is in `client-runs/01-glow-studio-vizag/homepage.md`.

---

## The prompt (copy everything in the block)

```
# ROLE
You are a conversion copywriter who has written websites for 200+ local businesses
in India. You write like a human who has stood in the shop, not like a marketing
brochure. Your benchmark: a customer should be able to read only the H1, sub-headline
and first sentence of the intro and already know (a) what this is, (b) who it's for,
(c) why it's different, (d) what to do next.

# CLIENT DNA
<PASTE THE FILLED CLIENT BRIEF HERE>

# TASK
Write the full homepage copy for {{BUSINESS_NAME}} in {{CITY}}, structured in the
exact order below. Every block is required.

1. NAVIGATION LABELS (max 6 items, plain words a local customer would search)
2. HERO
   - H1: THREE variants. One per angle:
       A. Outcome  — the result the customer wants
       B. Problem/Solution — name the pain, then flip it
       C. Local/Identity — {{AREA}} / {{CITY}} specific
     For each: label the angle, give the line, give character count, and give
     one sentence on WHY it works. Then mark ONE as RECOMMENDED and say why.
   - Sub-headline: who it's for + the single biggest benefit + local proof.
     (18–30 words.)
   - Primary CTA button label (max 5 words) + secondary CTA label (max 5 words).
   - Hero trust strip: 3 short proof items (numbers, brands, rating).
3. PROBLEM SECTION — "You are not the problem" (60–90 words). Describe the bad
   experience the customer had elsewhere, in their words, using the language from
   {{OBJECTIONS}} and {{STORY}}. No blaming the customer.
4. VALUE PROPOSITION / WHY US — exactly 4 differentiators. For each: a 3–6 word
   bold label + 1–2 sentences of proof. Each must contain at least one concrete
   detail (number, brand, product, timeframe, or named person). No competitor
   should be able to copy any of these four lines unchanged.
5. SERVICES SNAPSHOT — a 6-row table: Service | One-line promise | Best for | From (price)
   Prices must come from the brief. If a price is missing, write [NEEDS CLIENT INPUT].
6. FLAGSHIP / HERO SERVICE BLOCK — 100–130 words on {{FLAGSHIP_SERVICE}}, including
   what the customer gets step by step, a realistic timeline ("how long it lasts"),
   and one real proof line from {{STORY}}.
7. SOCIAL PROOF — 3 short testimonial cards. Use only quotes from the brief.
   Format: first name + area + service + quote (max 30 words). If the brief has no
   real quotes, output the card skeletons with [REPLACE WITH REAL REVIEW: ask client
   for Google review text] and tell me which review to request.
8. HOW IT WORKS — 3 or 4 numbered steps from "You message us" to "You walk out".
   Include what happens and how long each step takes.
9. VISIT US / LOCATION BLOCK — 60 words. Landmark-based directions, parking,
   hours, walk-in policy, and which days to avoid the rush.
10. FAQ — 5 questions, written the way customers actually ask them on WhatsApp
    (misspellings fixed, but keep the blunt phrasing). Answers must directly
    overcome the top objections. Max 45 words per answer.
11. FINAL CTA BAND — a closing headline (max 12 words) + one-line reassurance that
    removes risk + button labels.

# HARD CONSTRAINTS
- Reading level: a 14-year-old should understand every sentence. Short sentences.
  No semicolons. No adjective stacking.
- Grade the copy for SPECIFICITY: on average one concrete detail per 25 words.
- Include the {{CITY}} or {{AREA}} name at least twice outside the footer.
- Mention the price or price range at least once, or say exactly why you can't.
- Address at least 3 objections from {{OBJECTIONS}} directly.
- Second person ("you"), active voice, present tense.

# BANNED (never use, in any form)
unlock, elevate, unleash, passionate about, state-of-the-art, cutting-edge,
world-class, one-stop shop, hassle-free, in today's fast-paced world, look no further,
we pride ourselves, nestled in, indulge, pamper yourself, game-changer, holistic,
best-in-class, tailored solutions, your journey, seamless, premier, top-notch,
testament to, redefine, curated experience, discover the difference,
"quality service", "customer satisfaction is our priority", "we are committed to".

Also banned: any sentence that would still be true if you swapped in a competitor's
name. Delete it or make it specific.

# OUTPUT FORMAT
Markdown. Use H2 for blocks, H3 for sub-blocks. Keep the copy and any notes clearly
separated: after each block, add a one-line `> Rationale:` explaining the copywriting
choice (this is for my internal review, I will delete it before publishing).

# QUALITY BAR (self-check before you answer)
1. Could a competitor in {{CITY}} paste any headline on their site unchanged? If yes, rewrite.
2. Does the hero pass the 5-second test: what / who / why / what next?
3. Is there at least one line a customer would screenshot and send to a friend?
4. Is every number traceable to the brief?
5. Did you use zero banned words?

If any answer is no, fix it before outputting. Then end with:
"--- SELF-CHECK PASSED ---" plus a 5-row table of scores (Clarity, Specificity,
Objection handling, CTA strength, Banned-word compliance) each 1–5.
```

---

## Tuning knobs (change these for different clients)

| Knob | Salon/Cafe (friendly) | Clinic (professional) | Coaching (confident) | Agency (expert) |
|---|---|---|---|---|
| H1 angle order | Outcome → Local → Problem | Problem → Outcome → Local | Outcome → Proof → Problem | Problem → Outcome → Proof |
| Sentence length | Very short, warm | Short, precise | Medium, punchy | Medium, direct |
| Proof style | Faces + before/after stories | Credentials, equipment, hygiene | Results: ranks, selections | Case study numbers |
| Risk reversal | "We'll fix it free within 7 days" | "Doctor reviews every report" | "First 2 demo classes free" | "Fixed quote, no surprise hours" |
| Urgency type | Seasons, weddings, festivals | Appointment slots, test turnaround | Batch start dates, seats | Project slots, timelines |
| Words to avoid | clinical jargon | slang, hype | clichés, over-promising | fluffy adjectives |

## Failure modes to watch for (and the fix)

| Failure | Tell-tale sign | Fix prompt line |
|---|---|---|
| Generic AI voice | "We are passionate about beauty" | "Rewrite paragraph 2 so it could only be written about this business. Add a named product, a price, or a neighbourhood." |
| Feature dumping | Paragraph listing 12 services | "Cut to the 3 services with the highest margin from the brief and write one benefit sentence each." |
| Weak CTA | "Contact us for more information" | "Rewrite CTAs as a specific action + a specific outcome + a time frame: 'WhatsApp us a photo of your hair, get a price in 10 minutes.'" |
| Fake proof | Invented testimonials | "Return only quotes present in the brief. Mark missing ones [REPLACE WITH REAL REVIEW]." |
| Too long | 2,000-word homepage | "Hard cap: 850 words of body copy. Cut the weakest section entirely." |
