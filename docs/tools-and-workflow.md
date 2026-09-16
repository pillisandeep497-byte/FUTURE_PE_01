# Tools & Workflow — what was used, and how

---

## 1. The AI models

| Tool | Link | Role in this project | Notes from use |
|---|---|---|---|
| **Claude** | claude.ai | Primary long-form generation: homepage, services page, CTA blocks | Best banned-word compliance — it self-corrects before outputting. Best at keeping to the requested markdown schema. Handles Indian local context well when the brief is specific. |
| **ChatGPT** | chat.openai.com | Tone adaptation across business types + the QA/banned-phrase scan | Excellent at structured critique. The QA prompt ("flag any sentence that stays true if you swap the business name") works noticeably better here than elsewhere. |
| **Gemini** | gemini.google.com | Local SEO: meta tags, keyword map, FAQ, answer-engine snippets | Strong at breaking keywords into intent groups. Occasionally too formal in CTAs — re-prompt with "write it the way a customer would say it". |

**Cross-check method:** each model was given the *same* brief file. Any factual detail that appeared in one output but not the brief was treated as an invention and removed. This is the practical defence against hallucinated proof.

---

## 2. The web builders (where this copy gets published)

**Lovable — lovable.dev**
- Paste the copy section by section, not all at once: hero → value → services → CTAs → FAQ → contact.
- Prompt pattern that works: *"Use this exact copy for the hero. Do not rewrite it. Create a two-column hero: left = headline, sub-headline, two buttons, trust strip; right = photo."*
- Then: *"Keep all text exactly as given. Change only layout, spacing and colours."*
- Watch out: AI builders paraphrase. Say "use this copy verbatim" in every single message, and re-check the rendered page against `final-copy.md`.

**Framer AI — framer.com/ai**
- Framer is better for a visually polished one-page site, Lovable for anything with booking logic.
- Build the section order first, paste copy in second. Framer's AI is more likely to keep your text intact if the layout already exists.
- Add the WhatsApp click-to-chat as a sticky button (`wa.me/91XXXXXXXXXX?text=...`) — this converts better than a contact form for local businesses in India.

**WordPress (alternative)**
- Use a block theme (Kadence / Blocksy / Astra). Each markdown section becomes a block. Meta tags via Rank Math — paste from Appendix A of `final-copy.md`.

---

## 3. The workflow, end to end

```
1. INTAKE      prompts/00 → owner call or site visit → brief.md filled
                          (never skip; this is where the quality is created)

2. RECON       Google Maps reviews + Instagram + competitor sites
                          (comes before writing, not after)

3. GENERATE    prompts/01 → homepage.md
               prompts/02 → services.md
               prompts/03 → ctas.md
               prompts/05 → seo-meta-faq.md

4. ADAPT       prompts/04 → tone variants (only if the business type differs)

5. QA          prompts/06 → banned-phrase scan + 25-point scorecard
                          → fix every High-severity flag

6. HUMAN PASS  add 3 facts only a local person knows
               read aloud, cut anything you stumble on
               verify every number and flag anything unverified

7. PACKAGE     final-copy.md (client deck, flags consolidated)
               preview/index.html (visual mockup)
               README.md (repo)

8. SHIP        push to GitHub → LinkedIn post → client pitch
```

**Time budget per client once the system exists:** ~2.5 hours (30 min intake, 60 min generation + editing, 30 min QA, 30 min packaging). That's what makes this a viable service — the same workflow scales across clients without rewriting the prompts.

---

## 4. Prompts that produced the best results (for reuse)

**The single most valuable line in the whole system:**
> *"Any sentence that would remain true if you swapped the business name for a competitor's name — mark it GENERIC and rewrite it."*

**The second most valuable:**
> *"Do not invent facts, prices, awards, testimonials or certifications not present in the brief. Write `[NEEDS CLIENT INPUT: ...]` instead of guessing."*

**The third:**
> *"Include one honest line about who this service is NOT right for. This builds more trust than any adjective."*

---

## 5. Cost & access notes

- All three AI tools were used on free tiers — enough for this task. Claude and ChatGPT free tiers handle the prompt lengths used here (the brief + prompt together stays under ~3,000 tokens).
- GitHub repo: free, public.
- Domain (optional, for a real client site): ₹700–₹1,200/year. Hosting via Lovable/Vercel/Framer free tier is sufficient for a local business site.
- **Total cost of a client-ready local business website with this system: under ₹1,500 + your time.** That number is worth saying out loud in your LinkedIn post and your pitch — it's the reason a salon owner says yes.
