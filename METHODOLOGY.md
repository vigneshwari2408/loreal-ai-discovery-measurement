# Methodology

How this analysis was built, what's proven versus proposed, and where its limits are.

## 1. The core data

Everything in this project traces back to two things L'Oréal actually discloses every year: total sales and e-commerce sales, both reported and like-for-like (LFL). These are pulled directly from L'Oréal's Annual Reports, Annual Results press releases and the 2025 Universal Registration Document, 2021–2025, and live in `01_LOreal_Data` in the workbook — every other tab either references those cells or clearly marks itself as independent context.

**One rule governed every cell in this project: an unknown value stays blank. It never becomes zero.** The 2025 e-commerce figure is a case in point: the 2025 Annual Results release said only that e-commerce had passed 30% of sales, so the value was left blank until the exact figure could be verified. L'Oréal's 2025 Universal Registration Document reports it — €13.3 billion in e-commerce sales, 30.2% of Group sales — and that disclosed figure is now used in the workbook, the chart, and the deck. (An earlier draft of the workbook actually violated this rule in a few downstream formulas that silently read a blank cell as zero — caught during a full audit pass and fixed before this version.)

## 2. Reported growth vs. like-for-like growth

These are two different questions. Reported growth includes currency and scope effects (acquisitions, disposals); LFL growth holds those constant. The deck and workbook both keep these as separate columns rather than picking one and calling it "growth" — conflating them is a common analyst mistake this project deliberately avoids.

## 3. CAGR and indexing — read together, not separately

Total sales CAGR (2021–2025, 4 years) is 8.08%. E-commerce CAGR (2021–2025, 4 years; €9.3B to €13.3B) is 9.36%. **Both cover the same 2021–2025 window** — the period is stated explicitly wherever the numbers appear. The indexed growth chart (both series rebased to 100 in 2021) exists specifically to show what the CAGR comparison alone would hide: total sales pulled further ahead through 2023 before e-commerce closed most of the gap by 2024 and ended 2025 at 143.01 against 136.44 for total sales.

## 4. External context — used only where genuinely comparable

Two outside datasets appear in the appendix: FRED's U.S. Health & Personal Care Retail series, and Eurostat's consumer and enterprise digital-adoption series. Both are explicitly labeled **contextual, not benchmark-grade**, for a specific reason: FRED is U.S.-only and category-level (not L'Oréal-specific or global); Eurostat measures general online-purchase behavior, not beauty spending. Neither is treated as proof of anything about L'Oréal — they're there to show whether the company's own trajectory is broadly consistent with wider retail/digital trends, and no further than that.

One real finding survived this comparability check: in Spain, 2024→2025, *consumer* online-purchase adoption rose (+2.95pp) while *enterprise* B2C web-sales adoption fell (−1.24pp) — the same market, opposite movement, on two different but related indicators. It's included as a documented observation, not a causal claim.

## 5. Attribution vs. incrementality

A purchase tagged "AI-referred" is evidence a tracking signal fired — not evidence the AI referral *caused* the purchase. That distinction is the spine of the measurement framework: a comparison-group test is what separates the two, not a better tracking tag.

## 6. The AI evidence audit

Every AI-related claim used in this project is classified into one of three tiers, checked against public evidence directly (not assumed):

- **Announced** — L'Oréal's own public statements (the OpenAI partnership, discovery initiatives, virtual try-on, the ad pilot's existence)
- **Documented** — real, current OpenAI platform documentation (e.g., ChatGPT Ads now supports country/state/DMA-level geographic targeting and has published reporting-metric definitions)
- **Unknown** — specifically, whether *L'Oréal's* particular placement has been granted that level of access, targeting, or reporting. Platform capability and a specific advertiser's access to that capability are two different facts, and this project never collapses them into one.

## 7. Where I corrected myself mid-project

The pilot design originally assumed a geo-holdout test could simply be designed and run. Checking that assumption against public evidence showed the targeting and reporting granularity needed for a geo-holdout weren't confirmed for L'Oréal's specific placement — so the pilot's first stage became a feasibility check, not an assumption. The recommendation changed because the evidence didn't support the original design, not the other way around.

## 8. Known limitations

- No correlation coefficient is calculated anywhere in this project. Sample sizes (4–5 annual data points) are too small for that to mean anything, and it isn't attempted.
- External datasets are directional context, never a like-for-like L'Oréal benchmark — restated wherever they appear.
- The six-layer measurement framework and the pilot design are **proposals**, evaluated against what's publicly knowable — not a description of any measurement system L'Oréal currently operates.
- All figures are public-company disclosures and public government/EU statistical data. No proprietary, confidential, or scraped data is used anywhere in this project.

Full source list, with links and exactly what each dataset does and doesn't support: [SOURCES.md](./SOURCES.md).
