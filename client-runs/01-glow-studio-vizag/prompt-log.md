# Prompt Log — which prompt produced which section

Full transparency for the reviewer: the exact chain of prompts used, the model, and what needed human editing.

| # | Prompt file | Output file | Model used | Notes |
|---|---|---|---|---|
| 1 | `prompts/00-client-intake-brief.md` | `brief.md` | Claude (Sonnet class) | Ran the 12-question intake, then filled the brief template. |
| 2 | `prompts/01-homepage-copy.md` | `homepage.md` | Claude; cross-checked on ChatGPT and Gemini | 3 H1 variants generated, 1 selected by me with reasoning. |
| 3 | `prompts/02-services-page-copy.md` | `services.md` | Claude | 9 service blocks + comparison table + 3 packages. |
| 4 | `prompts/03-cta-trust-blocks.md` | `ctas.md` | Claude | 10 CTA blocks in one pass. |
| 5 | `prompts/05-seo-meta-faq-local.md` | `seo-meta-faq.md` | Gemini | Character counts verified manually. |
| 6 | `prompts/04-tone-and-language-adapter.md` | `../adaptability-proof.md` | ChatGPT | Same structure re-voiced for 4 other business types. |
| 7 | `prompts/06-editorial-qa-scorecard.md` | `qa-scorecard.md` | ChatGPT + manual | Scanned the raw draft, logged 10 flagged lines, fixed all High severity. |
| 8 | — | `final-copy.md` | Manual assembly | Client-facing version: all rationale notes removed, flags consolidated. |

## Model comparison (a useful section to include — few interns do this)

| Aspect | Claude | ChatGPT | Gemini |
|---|---|---|---|
| Compliance with banned-word list | Strongest — self-corrects mid-generation | Good, needs one re-prompt | Good, occasionally reintroduces clichés in CTAs |
| Following the exact output schema | Best | Very good | Good |
| Indian local-business tone | Very good when the brief is specific | Good | Good, sometimes too formal |
| Price transparency handling | Best — keeps numbers without hedging | Good | Tends to write "affordable" |
| Character counting for meta tags | Approximate — always re-verify | Approximate | Approximate |
| Best use in this project | Homepage, services, CTA copy | Tone adaptation, QA scan | SEO/meta/keyword work |

**Practical workflow that worked:** Claude for the long-form page copy → Gemini for the SEO layer → ChatGPT for the QA scan and the tone adaptations. Same brief, three models, each used where it was strongest. Keep the brief in a file and paste it each time so every model works from identical facts.

## What I changed by hand (the honest 20%)

1. Cut 4 brochure sentences the read-aloud test caught.
2. Added the landmark directions ("above Sri Sai Bakery") and the weekday walk-in window.
3. Rewrote all 5 CTAs — the raw outputs were still too close to "Book now".
4. Replaced every vague "premium/branded products" line with actual brand names.
5. Converted 3 invented-sounding testimonials into clearly-marked placeholders with a plan to collect real ones.
6. Removed the exclamation marks (there were 7 in the raw draft).
7. Added `*(verify)*` flags to every number that didn't come from a rate card.
