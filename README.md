# AI Mentor Bootcamp - Tejomurthula Naga Sai Satyanarayana Murthy

Public portfolio of 12-day AI Trainer Workshop. By Day 12: 6 daily notebooks + capstone Streamlit URL.

## Day 1 - Setup complete

- Google AI Studio API key provisioned
- Groq API key provisioned
- Hello-Gemini call working — see [Day1_Setup.ipynb](Day1_Setup.ipynb)
- Hello-Groq call working -see [Day1_Setup1.ipynb](Day1_Setup1.ipynb)
- 2-tool responces from Lab 1B: see screenshots below

This is Gemini responce
![Gemini first call](gemini_first_call.png)
And this is Groq responce
![Groq first call](groq_first_call.png)

## Day 2 - Six Pattern Drills

- Learned and practiced six prompt engineering patterns: Persona, Few-Shot, Chain-of-Thought, Structured Output, System Prompt, and Prompt Chaining.
- Explored how each pattern changes the style, clarity, and usefulness of AI responses.
- Main takeaway: Prompt Chaining and Structured Output were the most effective for generating clear, reusable, and well-organized outputs.

## Day 2 - JSON Resume Extractor

Completed the Lab 2B Turnkey Walkthrough. Built a pipeline to extract structured JSON from raw resume text using Gemini's structured-output API and Pydantic validation.

The Day2 task completed [Day2_ResumeExtractor.ipynb](Day2_ResumeExtractor.ipynb)

### Errors Handled & Edge Cases Addressed:
1. **Markdown fence wrapping** (`` ```json ... ``` ``): 
   Implemented a fallback retry prompt that asks Gemini to output raw JSON without fences. This handles cases where the model disobeys the `application/json` mime type constraint.
2. **Hallucinated phone number when source has none**: 
   Utilized `Optional[str] = None` in the Pydantic schema so the model can safely return `null` and pass schema validation without inventing a fake number.
3. **Empty / whitespace-only input**: 
   Structured the caller function to gracefully catch the `ValidationError` with "Field required" thrown by Pydantic when receiving blank input instead of crashing the pipeline.

**Sample resumes processed: 3 / 3 successful**

## Day 3 - Verification Chain

Completed the Lab 3A Turnkey Walkthrough on AI hallucination and fact-checking. Conducted a 3-step verification chain (AI Generation → Perplexity Check → Primary Source) on AI-generated placement statistics.

The completed verification matrix and reflection are documented in [Day3_Verification.md](Day3_VerificationChain.md).

### Key Takeaways & Findings:
1. **Confidence does not equal correctness**: Discovered that the most authoritative-sounding claims (complete with specific years and organizational attributions) were often partially or entirely fabricated by the LLM.
2. **AI Search is fallible**: Even tools like Perplexity that cite sources can link to summaries or unrelated datasets that don't actually support the core claim.
3. **The Human Verification Step**: The final verification step belongs to the human every time; you must open the primary source and check the specific numbers/context directly.

## Day 3 - Placement-Cell AI Policy

Completed the Lab 3B Turnkey Walkthrough. Authored a 1-page enforceable AI-use policy for a college placement cell, classifying 8 student-AI scenarios using EU AI Act risk tiers.

The final policy is available as [Day3_AI_Policy.pdf](Day3_AI_Policy.pdf).

### Policy Structure:
- **8 scenarios tiered** using the EU AI Act framework (Unacceptable · High-risk · Limited · Minimal)
- **6 Permitted Uses** — each a single sentence with verb + object + condition
- **4 Prohibited Uses** — each paired with a concrete, enforceable detection method
- **Enforcement** section — honest about what the placement cell can and cannot detect

### Key Design Decisions:
1. **Only 2 of 8 scenarios are Unacceptable** (AI-generated CGPA on resume, AI-cloned voice for video interview) — both involve clear identity or record falsification. Over-banning everything is unenforceable.
2. **Detection-first prohibited rules**: Every "may NOT" rule has a named detection method. Rules without a detection method were not written.
3. **1-page constraint held**: The policy fits on a single A4 page — a policy that runs 4 pages doesn't get read by students or staff.
