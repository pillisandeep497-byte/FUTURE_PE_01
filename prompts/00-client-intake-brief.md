# PROMPT 00 — Client Intake Brief (the feeding prompt)

> **Why this exists:** AI copy sounds generic because the input is generic. This prompt extracts the raw material that makes copy specific. Fill it once per client; every other prompt in this system consumes it.
> **How to use:** Paste this prompt into ChatGPT / Claude / Gemini and answer as the business owner. Or use the 12 questions below as your site-visit / phone-call script and type the answers in manually.

---

## PART A — Paste-ready intake prompt

```
You are a senior brand strategist doing a discovery call with a local business owner.
Your job is NOT to write copy yet. Your job is to extract raw material.

Ask me the questions below ONE AT A TIME. After my answer, ask a follow-up until
you have something concrete, specific and non-generic. Push back on vague answers:
- If I say "good service", ask "what specifically happens here that doesn't happen
  at the salon down the road?"
- If I say "affordable", ask "what is the actual number, and cheaper than whom?"
- If I say "experienced", ask "how many years, how many customers, one example?"

RULES
1. One question per message. Never ask two at once.
2. Never compliment my answer. Just dig deeper.
3. If I don't know a number, make me estimate and mark it [ESTIMATE].
4. Stop after Question 12 and output the completed CLIENT BRIEF in the exact
   markdown template I give you at the end.

THE 12 QUESTIONS
1. What is the business called, what exactly do you sell, and where are you located
   (area + city)?
2. Who is your best customer — describe one real person who walked in last month.
3. What are the top 3 things people come to you for? Give the exact service names
   and prices you charge.
4. What is the #1 reason customers choose you over the shop/business next door?
   (Not "quality". Something a competitor cannot say.)
5. What do customers complain about or fear BEFORE they come to you? Recall the
   hesitant questions you hear on the phone.
6. What is the most common mistake or bad experience customers had elsewhere?
7. Tell me one customer story that made you proud. Real name/first name, what
   happened, what the result was.
8. What brands/products/machines do you use? Name them exactly.
9. How many years in business, how many customers served, or any award/rating?
10. What do you want a website visitor to DO — call, WhatsApp, book online, walk in,
    fill a form? What happens after they do it?
11. Is there a season, offer, or time-sensitive reason to contact you now?
12. What three words describe how you want to sound — and what three words describe
    how you do NOT want to sound?

AFTER QUESTION 12, OUTPUT THIS EXACT TEMPLATE:

# CLIENT BRIEF — {{BUSINESS_NAME}}
## 1. Identity
- Business name:
- Category (salon / cafe / clinic / institute / agency / other):
- City, neighbourhood, landmarks:
- Years operating:            [verified / ESTIMATE]
- Team size / who does the work:
## 2. Customer
- Primary customer (one paragraph, specific):
- Secondary customer:
- What they want emotionally (look/feel/status/relief):
- What they fear:
## 3. Offer
| Service | Real name they use | What's included | Duration | Price | Margin/priority |
- Flagship service (the one to push):
- Entry-level/lead service (low-risk first step):
- Premium service (profit driver):
## 4. Differentiation
- Unique mechanism (what they do that others don't):
- Proof points (numbers, brands, certifications):
- Proof stories (1–3, verbatim where possible):
## 5. Objections & fears (ranked)
1. 2. 3. 4.
## 6. Goals
- Primary conversion action:
- Secondary conversion action:
- Seasonal/urgency hook:
## 7. Voice
- Tone (choose from: friendly / professional / confident-simple / warm-clinical / premium-calm):
- Language: English / Telugu-English mix / Hindi-English mix / other:
- Must-sound-like (3 words):
- Must-NOT-sound-like (3 words):
- Words the owner hates & never uses:
## 8. Channels
- Website/Instagram/Google listing links:
- Top 3 competitors in the area:
## 9. Open questions to verify with client
- [list anything marked ESTIMATE or unverified]

Then say: "Brief complete. Ready for PROMPT 01 (Homepage)."
```

---

## PART B — Variables map (what the rest of the prompts consume)

Every downstream prompt references these tokens. Replace them with the brief values (or paste the whole brief and tell the model "treat the brief above as the source of these variables").

| Token | Meaning | Source | Example value |
|---|---|---|---|
| `{{BUSINESS_NAME}}` | Trading name | Q1 | Glow Studio by Sanjana |
| `{{CATEGORY}}` | Business type | Q1 | beauty salon & bridal studio |
| `{{CITY}}` | City | Q1 | Visakhapatnam |
| `{{AREA}}` | Neighbourhood + landmarks | Q1 | MVP Colony, near Sampath Vinayaka Temple |
| `{{YEARS}}` | Years operating | Q9 | 6 |
| `{{CUSTOMER}}` | Primary customer | Q2 | working women 24–40 + brides |
| `{{SIGNATURE_SERVICES}}` | Top 3 services w/ prices | Q3 | keratin from ₹4,500; HD bridal from ₹18,000 |
| `{{UNIQUE_MECHANISM}}` | Why-them | Q4 | 15-min consultation + free patch test + "we'll tell you no if it'll damage your hair" |
| `{{PROOF}}` | Numbers/brands/awards | Q8, Q9 | 4,500+ clients, 300+ brides, L'Oréal Professionnel, Schwarzkopf, O3+ |
| `{{STORY}}` | Real customer story | Q7 | ... |
| `{{OBJECTIONS}}` | Ranked fears | Q5, Q6 | price shock, damaged hair, upsell pressure, bridal trial mismatch |
| `{{PRIMARY_CTA}}` | Main action | Q10 | Book on WhatsApp, reply within 10 min |
| `{{URGENCY}}` | Seasonal hook | Q11 | wedding season Nov–Feb; trials fill 3 weeks ahead |
| `{{TONE}}` | Voice profile | Q12 | friendly |
| `{{LANGUAGE}}` | Language mode | Q12 | English with light Telugu warmth |
| `{{BANNED_WORDS}}` | Owner's hates + global banned list | Q12 | "cheap", "discount parlour" |

---

## PART C — Reuse instruction (put this at the top of every generation)

```
You are working from the CLIENT BRIEF pasted below. Treat it as the single source
of truth. Do not invent facts, prices, awards, testimonials or certifications that
are not in the brief. If a section needs information the brief does not have,
write the line as [NEEDS CLIENT INPUT: <what to ask>] instead of guessing.

CLIENT BRIEF
====================
<paste filled brief>
====================
```

**Why this matters:** this one instruction is what stops the model from writing "award-winning salon with 20 years of experience" for a 6-year-old studio. Reviewers of your task will look for exactly this kind of constraint.
