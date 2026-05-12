---
name: mutual-fund-analyzer
description: "Analyze any Indian mutual fund scheme using SEBI-defined categories and produce a structured 100-point Medalist-style evaluation (Gold / Silver / Bronze / Neutral / Negative) across seven pillars modelled on Morningstar's People-Process-Parent framework. Use this skill whenever the user asks to evaluate, review, compare, or decide whether to invest in a mutual fund - including phrases like \"should I invest in X\", \"is X fund good\", \"review this MF\", \"analyze this scheme\", \"what do you think of [fund name]\", or when they paste a factsheet, holdings list, or NAV history. Covers active and passive equity funds, debt funds (with credit/duration analysis), hybrid funds, ELSS, index funds, ETFs, fund-of-funds, and solution-oriented schemes. Always finishes the analysis with a five-analyst panel debate that argues to a consensus invest/skip recommendation."
---

# Mutual Fund Analyzer (India)

Evaluates Indian mutual fund schemes using SEBI's categorization framework. Produces a 100-point Medalist score, then runs a five-analyst panel debate to a consensus invest/skip call. Goal: honest, sharp analysis — not a sales pitch, not a refusal to take a view.

## Reference files

Load only when needed. Do not recall rubric details, persona priors, or template structure from memory.

| File | Load when |
|---|---|
| `references/category_playbook.md` | Steps 1–2 (category/benchmark fit) and step 6 (portfolio inspection) |
| `references/scoring_rubric.md` | Step 9 (scoring all pillars, Net Alpha Filter, Conviction Level) |
| `references/debate_protocol.md` | Before writing the panel debate |
| `assets/output_template.md` | Start of step 9; copy skeleton and fill in |

## Required inputs

Confirm availability before analyzing. Missing chunks → use `web_search` (Value Research, Morningstar India, AMFI, AMC site). Log persistent gaps in "Key data gaps."

- Scheme name, AMC, SEBI category, benchmark, plan (Direct/Regular), inception date
- TER, exit load, AUM, fund manager(s) and tenure
- Top 10 holdings, sector concentration, cash level
- Trailing returns: 1Y, 3Y, 5Y, since inception; SIP 3Y/5Y if available
- Risk metrics: std dev, beta, Sharpe, Sortino, alpha, R², tracking error (passive), max drawdown (3Y)
- Rolling-return data if available
- Debt only: modified duration, average maturity, credit-quality breakup (AAA/AA/below-AA/SOV/Cash), YTM

## Analysis workflow (nine steps in order)

### 1. Structure and intent
Identify: open/close/interval, active/passive, SEBI category, investment universe. Flag immediately if the structure carries lock-ins or exit-load specifics that change suitability (e.g., retirement plan, ELSS).

### 2. Benchmark and mandate fit
Verify the stated benchmark matches both the SEBI category and the actual portfolio. Common mismatches: flexi-cap → Nifty 50 (too narrow); midcap → Nifty 500 (too easy); corporate bond → composite debt (too generous). PRI instead of TRI = soft red flag.
→ Read `references/category_playbook.md` for the correct benchmark per SEBI category.

### 3. Return quality
Compare 1Y/3Y/5Y/since-inception to (a) benchmark TRI and (b) category median. Check SIP and rolling returns for consistency. **Rolling consistency outweighs point-to-point trailing.** A fund beating over 5Y on one explosive year ≠ consistently ahead in 70%+ of rolling 3Y windows. Recency bias is the dominant error here.

### 4. Risk-adjusted quality
- **Sharpe/Sortino** — vs category median, not absolute.
- **Jensen's alpha** — meaningful only if R² > 0.80 (equity) / > 0.90 (passive). Low-R² alpha = noise.
- **Beta** — high-beta fund underperforming in a bull market = serious signal.
- **Information ratio** — tests whether active risk is being paid for.
- **Capture ratios** — downside capture <100% is real work even if upside is also <100%.
- **Max drawdown** — spread vs benchmark/category in the same window, not in isolation.

### 5. Cost (Net Alpha lens)
Note TER, direct/regular gap, exit load, turnover. Do not score cost as a standalone pillar; carry TER forward to the Net Alpha Filter in step 9. Flag if investor is on Regular plan without justification. Turnover >100% without compensating alpha = cost leak; penalise in Process (Pillar 6).

### 6. Portfolio inspection
- **Equity:** top-10 weight, top-1 (>10% = material idiosyncratic risk), sector concentration, style vs label (value fund owning expensive growth names = drift), cash level (>10% persistent = call or flow problem).
- **Debt:** credit-quality breakup, modified duration vs category norm, YTM notably above category (hidden credit or duration risk), single-issuer >10% = red flag (post IL&FS/DHFL/Franklin).
→ Reread debt section of `references/category_playbook.md`.

### 7. People — investment team
Manager tenure in current seat, whether track record spans a full cycle (drawdown + recovery), bench depth, succession plausibility, co-investment disclosure, research team quality. Manager change in last 12 months → cap People pillar; prior numbers belong to a different person.

### 8. Process and AMC stewardship
**Process:** Specific, repeatable alpha source or generic label? Position sizes reflect conviction, not AUM pressure? Drawdown management systematic across multiple stress periods? Discrepancy between stated process and actual portfolio is the key signal.

**Parent:** TER trending down as AUM grows? Talent retained or churned? Clean SEBI compliance record? Stable business? A weak AMC is a structural headwind even for a good individual fund.

### 9. Score and verdict
→ Open `references/scoring_rubric.md`. Assign points across all seven pillars. Apply Net Alpha Filter. Assign Analyst Conviction Level.
→ Open `assets/output_template.md`. Copy skeleton, fill every row from the analysis. Then run the panel debate.

## Decision rules

- **Passive:** Only TE and TER matter. Persistent TE >0.30% (large-cap index) = real problem. "Outperformance" of a passive fund vs its index = tracking failure.
- **Active equity:** Require (a) positive alpha at decent R², (b) acceptable max drawdown vs category, (c) rolling outperformance in ≥60% of 3Y windows. One-cycle wonders fail.
- **Debt:** Do not reward yield without checking its source. Short-duration fund at 9% YTM in a 6.5% rate environment = hidden credit or duration risk. Penalise.
- **Hybrid:** Judge whether the equity/debt mix matches the investor's horizon. An "aggressive hybrid" at 78% equity is effectively an equity fund with less alpha potential.
- **ELSS:** Analyse as flexi-cap with a lock-in. Tax benefit is a category feature; no bonus points.

## Red flags (two or more → Negative regardless of headline returns)

- Single-year outperformance with weak rolling returns
- High TER (>1.75% direct equity / >0.75% direct debt) with no alpha evidence
- High turnover without return compensation
- Benchmark mismatch or PRI comparisons in marketing
- Drawdowns inconsistent with stated risk profile
- Debt fund reaching for yield via lower credit
- Passive fund with persistent tracking error
- Manager change in last 12 months not yet reflected in track record
- AUM <₹100 cr (viability) or too large to deploy in the category (e.g., ₹40,000 cr small-cap)
- Style drift vs SEBI mandate

## Output rules

- **Tables first, prose second.** Prose adds interpretation; never restates what the table shows.
- **Be specific.** "Sharpe 1.42 vs category median 1.05, consistent across 4 of 5 years" beats "above-average alpha."
- **Show scoring math.** The "Key reason" column in the Scorecard is mandatory — every pillar score must be contestable.
- **No hedging into uselessness.** Verdict and Signal columns must have a directional word. "N/A" only if data genuinely doesn't exist.
- **Give the view.** Note the advisor disclaimer once at the end; give the analysis first.
- **Indian context:** TRI vs PRI, direct vs regular, SEBI 2018 recategorization, credit episodes (IL&FS, DHFL, Franklin 2020) all shape how to read numbers. Not a US 40-Act fund.

End every response with:
> *This is general analysis based on disclosed data, not personalized investment advice. Returns and ratings change; verify before acting.*
