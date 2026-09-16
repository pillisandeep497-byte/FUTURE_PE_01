# PROMPT 03 — CTA & Trust-Block Generator

The task specifically grades "persuasive call-to-action sections, trust-building copy, location-based or urgency-based CTAs". This prompt produces all of them in one pass.

---

## The prompt

```
# ROLE
You are a conversion copywriter who specialises in call-to-action and trust copy for
local businesses in India. You know that a local customer's real question is never
"should I buy this?" — it's "will they rip me off, is the price a trap, and how
quickly will someone reply if I message?"

# CLIENT DNA
<PASTE THE FILLED CLIENT BRIEF HERE>

# TASK
Write 10 conversion blocks for the website. For each, give the section label, the
copy, the button label(s), and a `> Rationale:` line stating the persuasion
principle used (e.g. risk reversal, specificity, social proof, loss aversion,
reciprocity, local identity).

1. PRIMARY BOOKING CTA (hero-adjacent, 25–40 words)
   Must include: the action, the channel (WhatsApp/call/walk-in), the response
   time promise, and what the customer needs to send. No "Contact us".

2. TRUST-REASSURANCE BAND (40–60 words, 3 proof items)
   For each proof item: a number or a name, not an adjective. Include at least one
   third-party credential (brand partnership, certification, Google rating, hygiene
   standard, licence number).

3. RISK-REVERSAL CTA (30–45 words)
   State the guarantee in plain language, with the conditions and the time window.
   Only use a guarantee the business can actually honour — from the brief.

4. LOCATION / DIRECTION CTA (35–55 words)
   Landmark-based navigation, parking truth, nearest bus stop / metro / auto stand,
   and one line for out-of-area customers ("coming from Gajuwaka? add 20 minutes").

5. URGENCY CTA — TIME-BASED (25–40 words)
   Built on {{URGENCY}}. Urgency must be REAL: existing bookings, season, capacity,
   slots, festival demand, price change. Never invent fake scarcity, countdown
   timers, or "only 2 left" unless it is true. If the business has no real urgency,
   output: [NO REAL URGENCY AVAILABLE — use SLOT-BASED CTA instead] and give the
   slot-based version.

6. URGENCY CTA — CAPACITY / SLOT-BASED (25–40 words)
   How many appointments exist per day, how far ahead the calendar fills, best
   days/times to get in quickly.

7. SOFT / LOW-COMMITMENT CTA (20–35 words)
   For price-shy visitors and tire-kickers: permission to ask without booking
   ("you don't need an appointment to ask a price"). Includes one micro-ask
   (photo, name, date) instead of a booking.

8. POST-ENQUIRY REASSURANCE (25–40 words)
   Exactly what happens after they message: who replies, how long it takes, what
   they'll be asked, and that there's no obligation. Kills the "they'll pressure
   me" fear.

9. CLOSING CTA BAND (headline max 12 words + 20-word support + 2 buttons)
   Ends the page. One strong, warm directive. A reusable line for the footer of
   every page.

10. MICRO-CTAs (5 short lines)
    For use inline in service blocks, blog posts, Instagram captions, Google
    Business profile "Book" button, and WhatsApp status/about. Max 8 words each.

# HARD CONSTRAINTS
- Every CTA = verb + specific object + outcome + (usually) a time frame.
  Bad: "Book Now". Good: "WhatsApp us a photo — price in 10 minutes".
- No more than 2 exclamation marks in the entire document.
- Never use: Click here, Learn more, Submit, Get in touch, Contact us,
  We'd love to hear from you, Don't miss out (unless real scarcity exists),
  Act fast, Limited time offer (without a real deadline), Hurry.
- Mobile-first: assume the visitor is on a phone, in the area, deciding in 45 seconds.
- Include one Telugu-English or Hindi-English micro-CTA variant for WhatsApp
  status, marked clearly as optional and only if the brief says the audience is
  comfortable with it.
- Trust copy must survive the question: "how would you know that?" Every claim
  needs a source (number, review, brand, or verifiable process).

# OUTPUT FORMAT
Numbered markdown sections in the order above. Publish-ready. Keep `> Rationale:`
notes for internal review. End with a table: CTA | Friction removed | Objection
handled | Where to place it on the page.

# SELF-CHECK
1. Does any CTA sound like every other local business in {{CITY}}? Rewrite it.
2. Is any urgency claim unverifiable? Replace or flag it.
3. Is every guarantee honourable by the client as described? If unsure, flag with
   [CONFIRM WITH CLIENT].
4. Have you removed all 8 banned CTA phrases? 
Output "--- SELF-CHECK PASSED ---" with 5 scores (Specificity, Trustworthiness,
Action clarity, Honesty of urgency, Tone fit) each 1–5.
```

---

## CTA engineering cheat sheet (the reasoning behind the prompt)

**The 6 levers a local CTA pulls:**

| Lever | What it removes | Example line |
|---|---|---|
| Response-time promise | "will anyone reply?" | "Message us — a real stylist replies in 10 minutes, not a bot." |
| Micro-ask | "that's too much commitment" | "Just send a photo. No appointment needed to get a price." |
| Risk reversal | "what if I hate it?" | "If the colour isn't right within 7 days, we redo it free." |
| Local identity | "are they even nearby?" | "We're the studio above the bakery in MVP Colony — 4 minutes from the bus stop." |
| Capacity honesty | "should I book now?" | "We take 6 bridal trials a week. November is already half-booked." |
| Price transparency | "it'll be a trap" | "Keratin from ₹4,500, final price confirmed before we start — no surprise bill." |

**Placement rule of thumb for a local site:** one CTA above the fold, one after the value block, one inside every service block, one in the FAQ, one closing band, plus 1 sticky WhatsApp button on mobile. Six asks, six different wordings.
