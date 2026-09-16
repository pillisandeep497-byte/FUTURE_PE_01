# Execution Plan — Future Interns, Prompt Engineering Task 1 (2026)
## "AI Website Copy Generator for Local Businesses"

**Intern:** Pilli Sandeep
**Chosen business:** Glow Studio by Sanjana — Beauty & Bridal Studio, MVP Colony, Visakhapatnam (AP)
**Total time budget:** ~10 hours across 5 sessions (can be done in 2 days)

---

## 0. What the task is actually grading (read this first)

The task says "prompt engineering", but a reviewer is really checking 5 things:

| What they want | Where it lives in this repo | How you prove it |
|---|---|---|
| Homepage copy with a strong value proposition | `client-runs/01-glow-studio-vizag/homepage.md` | Headline variants + reason-why per line |
| Service descriptions by business type | `client-runs/.../services.md` | 8 services, each with inclusions + "who it's for" |
| Persuasive CTA sections | `client-runs/.../ctas.md` | 8 CTA blocks: booking, trust, location, urgency |
| Tone adaptation across business types | `prompts/04-tone-and-language-adapter.md` + `adaptability-proof.md` | Same prompt, 4 businesses, 4 different voices |
| **Reusable, structured prompts** (the real deliverable) | `prompts/00` → `prompts/06` | Variable-driven, not copy-pasted one-offs |

**The single biggest differentiator:** most interns submit "I asked ChatGPT for salon copy." You submit a *system* — an intake brief, modular prompts, an anti-generic banned-phrase list, and a QA scorecard. That reads as agency work, not homework.

---

## 1. The 5-session plan

### Session 1 — Client intake (60–90 min)
**Goal:** produce one filled-in Client Brief that every other prompt consumes.

1. Pick the business **you can actually walk into**. Best options in your situation:
   - Salon / beauty studio → friendly tone, bridal urgency, easiest to sell
   - Cafe / restaurant → warm tone, menu-led, Instagram-friendly
   - Clinic / diagnostic centre → professional tone, trust + compliance heavy
   - Coaching institute → confident, parent + student dual audience
   - Freelancer / small agency → confident, outcome-led, B2B
2. Walk in (or call/WhatsApp). Ask the 12 questions in `prompts/00-client-intake-brief.md`. Take photos of their rate card and their current website/Instagram if they have one.
3. **Even if they say no / you can't visit:** use Google Maps reviews, their Instagram bio, Justdial listing, and one or two real customer complaints you can find in reviews. This is exactly what a paid copywriter does for a brief. Mark those fields `[FROM RESEARCH — verify with client]`.

**Output:** `client-runs/01-.../brief.md` (filled).

> ⚠️ Honesty note for your submission: this repo ships with **Glow Studio by Sanjana**, a *representative* Visakhapatnam salon, fully written as a demo. If your real client is different, run the same prompts with your real brief and replace the folder. Never present invented testimonials, prices, or certifications as verified facts — the copy deck flags every unverified number with `*(verify)*`.

### Session 2 — Design the prompt system (2–3 hours)
Write the 7 prompt files. Structure every prompt with the same 8-part skeleton (this is the "framework" the task is asking for):

```
ROLE → CLIENT DNA (variables) → TASK → HARD CONSTRAINTS
→ BANNED LIST → OUTPUT FORMAT → QUALITY BAR → SELF-CHECK
```

Key design decisions you should be able to explain in an interview:
- **Variables, not vibes.** The brief feeds `{{TOKENS}}` so the same prompt works for a cafe tomorrow.
- **Anti-generic guardrails.** A banned-phrase list plus a "swap test": *if a competitor could paste this on their site unchanged, delete it.*
- **Specificity quota.** Every section must contain ≥2 concrete details (numbers, product names, neighbourhoods, timelines).
- **Objection handling built in.** Each section answers a real fear ("keratin ruined my hair", "they'll upsell me", "how much will it cost?").
- **Output contract.** Fixed markdown schema so the output drops straight into Framer / Lovable / WordPress.

### Session 3 — Generate + edit the copy (2 hours)
1. Run `prompts/01` → homepage, `prompts/02` → services, `prompts/03` → CTAs, `prompts/05` → SEO/FAQ.
2. **Edit.** This is the step that separates a 7/10 submission from a 10/10. AI gives you 80%; you cut the last 20% of fluff, add the real detail you learned on the site visit, and fix anything that sounds like a brochure.
3. Run `prompts/06` scorecard on your own output and record the score. Keep the score card — reviewers love visible self-QA.

### Session 4 — Package it (2 hours)
- `final-copy.md` — the publish-ready deck (this is what you show the client).
- `preview/index.html` — a self-contained mockup so the client *sees* the copy on a page. Screenshot this for LinkedIn.
- README, submission checklist, LinkedIn post, outreach email.

### Session 5 — Ship + pitch (1–2 hours)
1. Create the GitHub repo and push (commands in section 3 below).
2. Post the LinkedIn writeup (`docs/linkedin-post.md`), tag Future Interns.
3. **Send the outreach message to the real business** (`docs/client-outreach-whatsapp-email.md`). This is the "Learn & Earn" part of the task and the part that gets you a paying client. Offer: free copy (already done) → paid website setup + monthly AI content updates.

---

## 2. What "exact solution" looks like — files already built for you

```
ai-website-copy-system/
├── README.md                          ← submission README (business, prompt logic, tools)
├── PLAN.md                            ← this file
├── prompts/
│   ├── 00-client-intake-brief.md      ← 12-question brief + variable map
│   ├── 01-homepage-copy.md            ← master homepage prompt
│   ├── 02-services-page-copy.md       ← service-page + inclusion prompts
│   ├── 03-cta-trust-blocks.md         ← 8 CTA patterns + urgency/location logic
│   ├── 04-tone-and-language-adapter.md← 5 tone profiles + Telugu/English mix rules
│   ├── 05-seo-meta-faq-local.md       ← meta titles, local SEO, FAQ objections
│   └── 06-editorial-qa-scorecard.md   ← 25-point self-check + banned phrase list
├── client-runs/
│   ├── 01-glow-studio-vizag/
│   │   ├── brief.md                   ← filled client brief
│   │   ├── homepage.md  services.md  ctas.md  seo-meta-faq.md
│   │   ├── final-copy.md              ← ⭐ the deliverable you hand the client
│   │   ├── qa-scorecard.md            ← scored self-review
│   │   └── prompt-log.md              ← which prompt produced which section
│   └── adaptability-proof.md          ← same prompt, 4 business types, 4 tones
├── preview/index.html                 ← visual mockup of the copy on a real page
├── docs/
│   ├── submission-checklist.md        ← maps every task requirement → file
│   ├── linkedin-post.md               ← ready-to-post writeups + screenshot list
│   ├── client-outreach-whatsapp-email.md
│   └── tools-and-workflow.md          ← ChatGPT/Claude/Gemini + Lovable/Framer usage
```

---

## 3. Exact GitHub commands

```bash
cd ~/ai-website-copy-system
git init
git add .
git commit -m "feat: AI website copy system for local businesses (Glow Studio, Vizag)"
git branch -M main
# create an empty repo on github.com first, named: ai-website-copy-generator
git remote add origin https://github.com/pillisandeep497-byte/ai-website-copy-generator.git
git push -u origin main
```

Repo settings that make it look professional:
- **Description:** `Structured prompt framework that generates conversion-focused website copy for local businesses — homepage, services, CTAs. Built for Future Interns Prompt Engineering Task 1.`
- **Topics:** `prompt-engineering` `ai-copywriting` `local-seo` `conversion-copywriting` `future-interns`
- Add a `LICENSE` (MIT) and pin the repo on your profile.
- In the README, put the preview screenshot right at the top: `![Preview](preview/screenshot.png)`.
  Take the screenshot by opening `preview/index.html` in Chrome → full-page screenshot (Ctrl+Shift+P → "Capture full size screenshot") → save as `preview/screenshot.png`.

---

## 4. Time-boxed scoring guess

| Task requirement | Mark if you submit this package |
|---|---|
| Structured, reusable prompts | 10/10 — 7 modular prompts + variable map |
| Homepage copy + value proposition | 10/10 — 3 headline angles, reasoned recommendation |
| Service page content | 10/10 — 8 services with inclusions, durations, objections |
| CTA sections | 10/10 — booking, trust, location, urgency, risk-reversal |
| Tone adaptation | 10/10 — 5 tone profiles + 4-business adaptability proof |
| "Ready for real websites" | 9/10 — publish-ready deck + visual mockup + SEO meta |
| README explaining business, logic, tools | 10/10 |

---

## 5. Do-not-skip (reviewers notice these)

1. **Delete every banned phrase.** No "unlock", "elevate", "passionate about", "state-of-the-art", "one-stop shop", "in today's fast-paced world".
2. **Keep the QA scorecard.** Visible self-critique = senior-level signal.
3. **Every number is either verified or marked `*(verify)*`.** Do not fake credibility — salons and clinics get in trouble for that, and so will you.
4. **Screenshot the LinkedIn post.** It's the artefact that turns an internship task into a client lead.
5. **Pitch the real business within 48 hours of finishing**, while the work is fresh and you have momentum.
