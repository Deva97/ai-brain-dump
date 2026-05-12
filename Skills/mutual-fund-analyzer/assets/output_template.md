# Output Template - Quick Reference

Copy-paste skeleton for the final response. SKILL.md has the canonical version with full instructions. This file is for quick recall during writing.

Rule: every section with numbers opens with a table. Prose follows to interpret — never to restate.

```markdown
# <Fund name> - Analysis

## Fund snapshot

| Field | Details |
|---|---|
| AMC | |
| SEBI Category | |
| Benchmark | |
| Plan | Direct / Regular |
| AUM | ₹X,XXX Cr (as of MMM YYYY) |
| TER | X.XX% |
| Inception Date | DD-MMM-YYYY |
| Fund Manager | Name (X yrs in seat) |
| Exit Load | |

[One sentence: what the fund does and who it is for.]

---

## Category and benchmark fit

| Check | Expected | Actual | Status |
|---|---|---|---|
| SEBI Category | | | ✓ / ⚠ |
| Benchmark index | TRI-based, correct for category | | ✓ / ⚠ |
| PRI vs TRI | TRI only | | ✓ / ⚠ |
| Portfolio style vs mandate | | | ✓ / ⚠ |

[One sentence: flag mismatches or confirm alignment.]

---

## Return quality

| Period | Fund | Benchmark TRI | Category Median | vs Benchmark | vs Category |
|---|---|---|---|---|---|
| 1Y | | | | | |
| 3Y | | | | | |
| 5Y | | | | | |
| Since Inception | | | | | |
| SIP 3Y | | | | | |
| SIP 5Y | | | | | |

Rolling: [X]% of 3Y rolling windows beat benchmark TRI over last 5Y.

[One paragraph: broad-based or single-cycle outperformance? Rolling consistency above 60%?]

---

## Risk-adjusted quality

| Metric | Fund | Category Median | Verdict |
|---|---|---|---|
| Sharpe Ratio (3Y) | | | Above / Below / In-line |
| Sortino Ratio (3Y) | | | |
| Beta | | 1.00 | |
| Alpha — Jensen's (3Y) | | | |
| R-squared | | | Meaningful if >0.80 |
| Std Deviation (3Y) | | | |
| Max Drawdown | | | |
| Upside Capture | | | |
| Downside Capture | | | |
| Information Ratio | | | Paid for if >0.50 |

[One paragraph: overall risk-reward picture. For passive funds, replace Alpha / IR / Beta with Tracking Error rows.]

---

## Portfolio quality

### Top 10 holdings

| # | Stock / Issuer | Sector | Weight % | Signal |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |
| 7 | | | | |
| 8 | | | | |
| 9 | | | | |
| 10 | | | | |
| **Top 10 total** | | | | |

### Sector concentration

| Sector | Fund % | Benchmark % | Active Bet |
|---|---|---|---|
| | | | Overweight / Underweight |

[One paragraph: concentration flags, style consistency, cash level, quality of holdings. For debt: swap tables for credit-quality breakup (AAA / AA / below-AA / SOV / Cash %) + modified duration vs category norm.]

---

## Cost and net alpha

| Item | Fund | Category Median | Context |
|---|---|---|---|
| TER — Direct | | | |
| TER — Regular | | | |
| Direct vs Regular gap | | | Which plan is the investor on? |
| Portfolio Turnover | | | High if >100% for equity |
| Exit Load | | | |

**Net Alpha:**

| | Value |
|---|---|
| Gross alpha estimate | ~X% |
| Minus: TER (Direct) | −X.XX% |
| **Net alpha** | **X%** |
| Filter result | Positive / Near-zero / Negative ↓ |

[One sentence: outcome of Net Alpha Filter. State if verdict downgrade triggered.]

---

## People

| Dimension | Finding | Signal |
|---|---|---|
| PM tenure in current seat | X yrs | Strong / Moderate / Weak |
| Cycle tested? | Yes / No / Partial | |
| Team depth / bench | Named deputy? Y / N | |
| Succession plausible? | Y / N | |
| Co-investment disclosed? | Y / N | |
| Research team quality | Dedicated / Generic / Thin | |

[One paragraph. Flag if manager change in last 12 months caps pillar at 9/17.]

---

## Process

| Dimension | Finding | Signal |
|---|---|---|
| Alpha source — stated | | Specific / Generic |
| Alpha source confirmed in portfolio? | Y / N / Partial | |
| Construction discipline | Conviction-sized / Momentum-chasing | |
| Unexplained turnover? | Y / N | |
| Drawdown management — systematic? | Y / N / Unclear | |
| Downside capture across 2+ stress periods | | <90% = good |

[One paragraph: genuine repeatable edge, or marketing language? State plainly.]

---

## AMC stewardship (Parent)

| Dimension | Finding | Signal |
|---|---|---|
| TER trend as AUM grew | Fell / Flat / Rose | |
| Direct plan support | Strong / Neutral / Weak | |
| NFO timing pattern | Clean / Peak-chasing | |
| PM retention | Low churn / Moderate / High churn | |
| SEBI compliance record | Clean / Minor issues / Material | |
| AUM trajectory | Growing / Stable / Declining | |
| Parent entity stability | Stable / Ownership uncertainty | |

[One paragraph: structural stewardship quality. A poor Parent is a long-run headwind; call it plainly.]

---

## Scorecard

| Pillar | Score | Max | Key reason |
|---|---|---|---|
| Mandate & Benchmark Fit | | 8 | |
| Return Quality | | 15 | |
| Risk-adjusted Quality | | 20 | |
| Portfolio Quality | | 12 | |
| People | | 17 | |
| Process | | 15 | |
| Parent (AMC Stewardship) | | 13 | |
| **Total** | | **100** | |
| Net Alpha Filter | — | — | Positive / Near-zero / Negative ↓ |
| Analyst Conviction | — | — | High / Medium / Low |

## Verdict: [Gold / Silver / Bronze / Neutral / Negative] — XX/100

[One sentence. State Net Alpha Filter downgrade or Low Conviction cap if either applied.]

## Key data gaps
[Anything material unavailable. If none: "None material."]

---

# Panel Debate

## Round 1 — Opening views

**Priya (Quant):** ...

**Anand (Value):** ...

**Meera (Skeptic):** ...

**Ravi (Cost Hawk):** ...

**Sneha (Suitability):** ...

## Round 2 — Cross-examination

**Priya (Quant):** ...

**Anand (Value):** ...

**Meera (Skeptic):** ...

**Ravi (Cost Hawk):** ...

**Sneha (Suitability):** ...

## Round 3 — Final votes

**Priya (Quant):** Invest / Skip / Conditional — <one line>
**Anand (Value):** ...
**Meera (Skeptic):** ...
**Ravi (Cost Hawk):** ...
**Sneha (Suitability):** ...

## Panel Verdict
<2-4 sentences: vote tally, real point of disagreement, final Invest / Conditional Invest / Skip>

---

> *This is general analysis based on disclosed data, not personalized investment advice. Returns and ratings change; verify before acting.*
```
