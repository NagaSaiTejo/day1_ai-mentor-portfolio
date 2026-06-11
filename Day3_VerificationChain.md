# Day 3 — Lab 3A: Verification Chain

## Verification Matrix

| # | Claim | AI Source | Perplexity Check URLs | Primary Source URL | Verdict |
|---|---|---|---|---|---|
| 1 | The average B.Tech placement package in Indian engineering colleges in 2025 was ₹6.2 LPA. | Gemini (citing NASSCOM) | https://www.perplexity.ai/search/average-btech-placement-2025 | https://community.nasscom.in/ *(no matching report found; original link was 404)* | NO PRIMARY SOURCE FOUND |
| 2 | 78% of Tier-1 college students received at least one placement offer in 2025. | Gemini (citing AICTE Annual Report) | https://www.perplexity.ai/search/aicte-placement-2025 | https://www.aicte-india.org/bureaus/planning/AnnualReport | PARTIAL |
| 3 | TCS hired approximately 40,000 freshers in 2025. | Gemini (citing TCS Annual Report) | https://www.perplexity.ai/search/tcs-fresher-hiring-2025 | https://www.tcs.com/investor-relations/annual-reports | VERIFIED |
| 4 | The IT services sector accounted for 56% of all engineering placements in India in 2025. | Gemini (citing NASSCOM) | https://www.perplexity.ai/search/nasscom-it-placements-2025 | https://community.nasscom.in/ *(no matching data found; original link was 404)* | FALSE |
| 5 | The median placement package at IITs in 2025 was ₹18.5 LPA. | Gemini (citing India Skills Report 2025) | https://www.perplexity.ai/search/iit-median-package-2025 | https://wheebox.com/india-skills-report *(India Skills Report does not cite IIT medians — AI cited wrong source)* | VERIFIED |

## Reflection

The claim that looked most authoritative but was actually weakest was claim #2: '78% of Tier-1 college students received at least one placement offer in 2025.' Gemini cited the AICTE Annual Report confidently, and Perplexity initially confirmed it by pointing to various news article summaries. But when I opened the actual AICTE placement statistics page, I found the 78% figure was not present — actual AICTE data for 2024–25 shows CS placement at 94.46%, not 78%. A second-level failure also emerged: the original AI-generated primary source URLs (nasscom.in/knowledge-center, wheebox.com/india-skills-report.htm) themselves returned 404 errors, meaning the AI hallucinated not just the statistics but the exact URLs too. The India Skills Report 2025 does not reference IIT median packages at all. Two layers of hallucination: wrong numbers AND wrong citations. The lesson: AI can sound authoritative at every layer — claim, source name, and URL — while being wrong at all three. The verification step belongs to the human — every time.
