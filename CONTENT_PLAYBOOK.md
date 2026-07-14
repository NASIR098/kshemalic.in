# KshemaLIC Content Playbook

## Every blog post must:
- Be written in BOTH English (src/content/blog/en/) and Kannada (src/content/blog/kn/), sharing the same `translationId`
- Use frontmatter matching the existing schema: title, description, date, category, tags, translationId, draft, imageKeyword
- Set `date` to the next available slot, spaced according to the site's publishing cadence (every 2-3 days), based on the most recent existing post's date — never duplicate or backdate
- Include 1-2 relevant `imageKeyword` terms in English (for the Pexels API fetch pipeline) even though the post itself may be Kannada
- End with a natural transition sentence inviting the reader to consult a certified LIC agent — do NOT repeat the IRDAI disclaimer text in the body, it's already rendered by the page template

## Factual accuracy rules (non-negotiable):
- Section 80C combined deduction limit is ₹1,50,000 per financial year — never state any other figure
- Section 10(10D) tax-free maturity ALWAYS requires stating the condition (premium ≤10% of sum assured for policies after April 2012) — never state maturity is tax-free unconditionally
- NEVER claim ULIPs, Index Plus, or any market-linked plan offers "guaranteed returns" — these are market-linked and must state that returns fluctuate with market performance
- NEVER invent a specific report/table citation (e.g., "Table 1.15") unless you can verify it exists — when citing LIC's claim settlement ratio, AUM, or solvency ratio, use ONLY these pre-verified figures and do not alter them:
  - Claim Settlement Ratio: 98.15% (FY 2024-25, IRDAI data)
  - Assets Under Management: ₹57.29 Lakh Crore (March 2026)
  - Solvency Ratio: 2.35 (March 2026; IRDAI-mandated minimum is 1.5)
- NEVER make disparaging or fabricated claims about competing insurers (no invented limits, no unverifiable comparisons)
- If a figure is needed that isn't in this file and can't be verified from official sources (IRDAI, Income Tax Act, LIC Act, RBI), phrase the point generally instead of stating a specific number

## Data visualization:
- Whenever the post includes comparative percentages, allocation breakdowns, or year-over-year figures, use the `<DataChart>` component (donut for proportions/allocations, bar for comparisons/trends) instead of relying only on a text table
- Import DataChart in .mdx posts only (not supported in plain .md)

## Images:
- Do not embed images directly — the `imageKeyword` frontmatter field is used by the existing Pexels fetch pipeline to auto-attach a featured image at build time
