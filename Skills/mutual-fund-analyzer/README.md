# Mutual Fund Analyzer (India)

A Claude skill for evaluating Indian mutual fund schemes against SEBI's categorization framework, then running a five-analyst panel debate that argues to a consensus invest / skip recommendation. It produces a 100-point Medalist-style score (Gold / Silver / Bronze / Neutral / Negative) across seven pillars modelled on Morningstar's People-Process-Parent framework, and finishes with a short panel debate where five analyst personas push back on each other before voting.

## What this skill does

When triggered, the skill walks Claude through a nine-step workflow: identify the fund's structure and SEBI category, check whether the stated benchmark is appropriate, evaluate return quality with a heavy weighting on rolling returns rather than point-to-point trailing returns, examine risk-adjusted metrics, look at cost through a net-alpha lens, inspect the portfolio for concentration and style consistency, assess the investment team, evaluate the AMC's stewardship of unitholder capital, and finally assign a score and verdict. After the structured analysis, the skill runs a debate among five personas (the Quant, the Value Investor, the Skeptic, the Cost Hawk, and the Suitability Analyst), each with distinct priors and characteristic concerns, and synthesises their votes into a final recommendation.

The skill is designed for Indian funds specifically. It builds in the Indian context — TRI versus PRI benchmarks, Direct versus Regular plans, the post-2018 SEBI re-categorisation, and the credit episodes (IL&FS, DHFL, Franklin Templeton's debt freeze) that shape how to read certain numbers — rather than treating Indian funds as if they were US 40-Act funds.

## When the skill triggers

The skill triggers whenever a user asks Claude to evaluate, review, compare, or recommend an Indian mutual fund. Typical phrasings include "should I invest in X fund", "is X fund any good", "review this scheme for me", "what do you think of [fund name]", or pasting a factsheet, holdings list, or NAV history into the conversation. It covers active and passive equity funds, debt funds with credit and duration analysis, hybrid funds, ELSS, index funds, ETFs, fund-of-funds, and solution-oriented schemes.

If the user only gives a fund name without data, the skill instructs Claude to fetch the latest factsheet from public sources (Value Research, Morningstar India, AMFI, AMC websites) rather than refusing.

## Folder structure

```
mutual-fund-analyzer/
├── README.md           ← this file (for humans)
├── SKILL.md            ← runtime instructions Claude reads when the skill triggers
├── references/         ← documents Claude consults mid-workflow
│   ├── category_playbook.md   ← SEBI category definitions, correct benchmarks per category
│   ├── scoring_rubric.md      ← 100-point breakdown across seven pillars
│   └── debate_protocol.md     ← five analyst personas and three-round debate format
└── assets/             ← templates used in the output
    └── output_template.md     ← copy-paste skeleton for the final structured response
```

The split between `references/` and `assets/` follows the Anthropic skill convention. A reference document is something Claude reads to inform its reasoning; an asset is something Claude copies into its output. Keeping `SKILL.md` short and pushing detail into these subfolders is a deliberate design choice called progressive disclosure — Claude only loads the deeper material when the workflow actually needs it.

## Maintaining the skill

To update any of the analytical framework — say, adjusting the scoring bands, adding a new SEBI category, or tweaking the panel debate format — edit the relevant file in `references/` rather than `SKILL.md` itself. The same goes for the output structure: changes to row order, new sections, or different labels belong in `assets/output_template.md`. Editing `SKILL.md` should mostly be reserved for the workflow logic itself or for adjusting the cross-references between files.

When making any change, keep `SKILL.md` under roughly 500 lines. If it starts pushing past that, the right move is usually to extract more detail into a new reference file rather than to keep growing the body.

## Disclaimer

This skill produces general analysis based on disclosed fund data. It does not constitute personalised investment advice. Returns, ratings, fund managers, and AMC quality all change over time, and any output from this skill should be verified against the latest factsheet and the user's own circumstances before any investment decision.
