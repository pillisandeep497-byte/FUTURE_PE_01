# LinkedIn Writeup — ready to post

Post after the repo is live. Attach 2–3 screenshots (visual mockup, prompt file, scorecard).

---

## POST 1 — the main submission post

> **I built a prompt system that writes website copy for local businesses. Here's what I learned about why most AI copy fails.** 🤖

> Most local businesses — a salon, a cafe, a clinic, a coaching centre — lose customers not because their service is bad, but because their website says nothing. "We provide quality service with customer satisfaction as our priority." Nobody has ever chosen a salon because of that sentence.
>
> For my Future Interns Prompt Engineering internship, I built a **reusable prompt system** instead of a one-off AI prompt.
>
> **The client:** Glow Studio by Sanjana — a hair and bridal studio in MVP Colony, Visakhapatnam. 7 years old, 4 chairs, 300+ brides. *(demo profile built as a working demonstration)*
>
> **What I learned: AI copy is generic because the INPUT is generic.**
>
> So I spent most of the effort on input quality:
> → A **12-question client intake brief** that forces specifics ("affordable" gets pushed back on until it becomes a real number)
> → A **banned-phrase list of 30+ AI clichés** that the model must self-check against
> → A **specificity quota** — one concrete detail per ~25 words
> → The **swap test**: if a competitor could paste this line on their site unchanged, delete it
>
> **The output closed the loop on the fundamentals:**
> • Homepage with 3 headline angles and a reasoned pick
> • 10 service blocks, each with what's included, honest timings, and a *disqualifier* ("if your hair can't take keratin, we'll say no") — the highest-trust line on the page
> • 10 CTA blocks: booking, trust, risk-reversal, location, and a real urgency CTA based on actual studio capacity, not a fake countdown
> • Prices written in text so Google can read them — the biggest SEO gap I found
>
> **QA:** I ran my own output through a 25-point scorecard. It scored 35/36 — and I logged the deduction. My raw first draft had **10 AI clichés** in it. The editing log shows every fix.
>
> One more thing that mattered: the system uses **five tone profiles** (friendly for salons and cafes, professional for clinics, confident-simple for coaching). I tested the same prompt on 5 business types — the copy is genuinely different each time, not just noun-swapped.
>
> The whole system + prompts + outputs are open-source in my repo 👇
> https://github.com/pillisandeep497-byte/ai-website-copy-generator
>
> If you run a local business in Vizag and want to see what this looks like for you, my DMs are open.
>
> Thanks to **@Future Interns** for the brief that pushed me to build a system rather than a prompt.
>
> #PromptEngineering #AICopywriting #FutureInterns #Copywriting #LocalBusiness #WebDevelopment #GenAI

---

## POST 2 — the "before/after" teaching post (post this 3–4 days later)

> **I asked AI to write copy for a Visakhapatnam salon. The first draft was embarrassing.**

> Here's the actual first line AI gave me:
> ❌ "We are passionate about helping you look your best with our state-of-the-art studio offering a wide range of premium services."
>
> Count the crimes: "passionate", "state-of-the-art", "wide range of", "premium". Four AI clichés in one sentence. And you could paste it onto 40,000 other salons' websites without changing a word.
>
> **Why does AI do this?** Because it's trained on the median of the internet, and the median local-business website is exactly this bad. If you don't force specificity, you get the average.
>
> Here's what I changed — and the three fixes anyone can use:
>
> **1. Replace adjectives with numbers.**
> ❌ "extensive experience" → ✅ "7 years in the same MVP Colony building"
>
> **2. Replace claims with process.** Anyone can claim quality. Nobody copies a process they don't actually run.
> ❌ "quality products" → ✅ "a patch test 24 hours before every colour service — no exceptions"
>
> **3. Give the customer a reason NOT to buy.** This felt wrong until I saw the result. Telling people when your service is *not* right for them is the fastest trust-builder in local service copy.
> ✅ "If your hair has been bleached twice in three months, keratin is the wrong first step. We'll tell you that on WhatsApp before you book."
>
> The version that came out of it: "Hair that behaves every morning. Makeup that survives a 12-hour wedding."
>
> Full prompt system in the comments. Built for the @Future Interns prompt engineering task.
>
> #Copywriting #PromptEngineering #AI #FutureInterns

---

## POST 3 — the "product" post (when you want a client)

> **What does a website copy audit reveal for a local business? I did one for a salon in Vizag.**

> I reviewed a fictionalised Visakhapatnam salon's online presence the way I'd audit a real client. Four gaps showed up, and all four are common:
>
> **1. No prices anywhere.** Customers asked the same question on WhatsApp 40 times a week. Publishing price ranges in text (not images) both reduces that load and ranks for "keratin price in Visakhapatnam" — a search with real buying intent.
>
> **2. No answer to the biggest fear.** For chemical services, the fear is damage. The site said "premium products". It never said "we'll tell you no if your hair can't take it."
>
> **3. No named person.** "Our team" everywhere. In local services, trust attaches to a person. Naming the stylist who does the work converts better than any adjective.
>
> **4. No reason to act now.** Not fake urgency — real capacity. "We take two 4-hour services a day" is a true constraint customers understand.
>
> I write these audits + the replacement copy as a service. 4 pages: homepage, services, CTAs, and local SEO metadata. Fixed price, delivered in a week.
>
> Message me if you'd like to see a sample. **@Future Interns** — this is the client-facing version of my Task 1 project.

---

## Screenshot list (what to attach)

1. **The rendered homepage mockup** — open `preview/index.html`, full-page screenshot. This is the single most convincing image.
2. **A prompt file open in your editor** — shows the structure (ROLE / CLIENT DNA / BANNED / SELF-CHECK). Proves it's a system, not a chat.
3. **The QA scorecard** — 35/36 with the editing log. Shows self-critique.
4. **The banned-phrase scan table** — 10 clichés found and fixed.
5. **The adaptability proof** — 5 businesses, 5 voices side by side.

**Formatting tips:** first line is the hook (LinkedIn truncates after ~2 lines). Use line breaks between every 1–2 sentences. Post between 9–11 AM IST on a weekday. Reply to every comment within the first hour — that's what drives reach. Tag Future Interns in the body, not just the comments.
