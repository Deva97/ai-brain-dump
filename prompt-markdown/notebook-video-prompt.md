# Educational Audio/Video Script Prompt

You are creating an educational audio/video script based on this research paper,
tailored for a senior software engineer with strong CS fundamentals but no prior
familiarity with this specific paper.

## Structure the content as follows:

### 1. HOOK (30 sec)
- Open with a real-world engineering problem this paper solves.
- Make it relatable: frame it as something I might face at work.

### 2. CONTEXT & MOTIVATION (2 min)
- What gap or limitation existed before this paper?
- What prior work does it build on? (Mention only the most important ones)
- Why does this matter to a practicing engineer, not just a researcher?

### 3. CORE IDEA — THE "AHA" MOMENT (3–4 min)
- Explain the key technical contribution in plain language first,
  then add precision.
- Use a concrete analogy or system design metaphor
  (e.g., load balancing, caching, distributed consensus).
- Avoid raw math — if a formula is critical, explain what it *does*,
  not just what it *says*.

### 4. METHODOLOGY — HOW THEY BUILT IT (4–5 min)
- Walk through the research approach: is this empirical, theoretical,
  a new system, a new algorithm, or a hybrid?
- Explain the key design decisions step by step:
  * What assumptions did the authors make, and are they reasonable?
  * What did they deliberately simplify or scope out, and why?
  * What is novel in their approach vs. borrowed from prior work?
- Highlight any clever engineering tricks or non-obvious choices.
- Call out trade-offs explicitly: latency vs. throughput,
  accuracy vs. speed, simplicity vs. generality.
- If there's a system architecture or pipeline, describe it like
  a design review: inputs, components, data flow, outputs.

### 5. HOW IT WORKS — UNDER THE HOOD (4–5 min)
- Walk through the algorithm, model, or mechanism step by step.
- For each major step, explain *what* it does and *why* it's needed.
- If there are multiple stages or phases, treat each one as a
  mini-explainer before zooming back out to the full picture.
- Highlight where the method is sensitive to hyperparameters,
  data quality, or scale — things that would bite me in production.

### 6. EXPERIMENTS — WHAT THEY TESTED & HOW (4 min)
- What was the experimental setup?
  * Datasets or environments used — are they realistic or toy?
  * Baselines chosen — are they fair and up-to-date comparisons?
  * Hardware/infrastructure used — does scale matter here?
- Walk through the key experiments one by one:
  * What hypothesis was each experiment testing?
  * What did the results actually show?
  * Were there ablation studies? What did removing each component reveal?
- Flag any weak spots:
  * Missing baselines or cherry-picked benchmarks?
  * Metrics that look good on paper but may not reflect real-world use?
  * Experiments run at a scale I couldn't replicate easily?

### 7. RESULTS & BENCHMARKS (2 min)
- What is the headline result — the number the authors are most proud of?
- How big is the improvement — is it meaningful in practice or marginal?
- Where does the method struggle or degrade? What are the edge cases?
- What limitations do the authors openly admit vs. what seems glossed over?

### 8. SO WHAT? — ENGINEERING TAKEAWAYS (2 min)
- Can I use this today? Is there an open-source implementation?
- What kind of system, scale, or domain does this apply to?
- What would it take to integrate this into a real production system?
- What should I watch out for or validate before trusting this in practice?

### 9. WRAP-UP (30 sec)
- One-sentence summary of the paper's contribution.
- One open question or future direction worth thinking about.

---

## TONE GUIDELINES:
- Conversational, like a senior engineer explaining to a peer over coffee.
- Intellectually honest — don't oversimplify to the point of being wrong.
- Move at a steady pace; pause to reinforce key ideas before moving on.
- Prefer active voice and concrete examples over abstract description.
- When covering experiments, think like a skeptical reviewer:
  praise what's rigorous, flag what feels hand-wavy.
