# Sources

Every dataset used in this project, what it supports, and what it doesn't.

## L'Oréal (primary source — supports full quantitative analysis)

| Source | Period used | Supports | Limitation |
|---|---|---|---|
| L'Oréal Annual Reports / Universal Registration Documents | 2021–2024 | Total sales, LFL growth, e-commerce sales/share/growth, operating margin | Company-reported; e-commerce definition held consistent across the series |
| L'Oréal 2025 Annual Results | 2025 | 2025 sales, reported/LFL growth, operating margin | Does not state the exact 2025 e-commerce figure — that comes from the 2025 Universal Registration Document (next row) |
| L'Oréal 2025 Universal Registration Document | 2025 | 2025 e-commerce sales of €13.3 billion, 30.2% of Group sales | Company-reported; e-commerce definition as used by L'Oréal across the series |
| L'Oréal × OpenAI announcement, 17 June 2026 (VivaTech) | 2026 | AI-powered discovery, virtual try-on, and advertising initiatives | Establishes public scope of the partnership; L'Oréal's specific measurement implementation is not detailed in this or any public source |

L'Oréal's investor relations site: **https://www.loreal-finance.com**

## External context (directional only — never a L'Oréal benchmark)

| Source | Dataset ID | Period | Supports | Limitation |
|---|---|---|---|---|
| U.S. Census Bureau via FRED | `MRTSSM446USS` | 2021–2025 (monthly, aggregated to annual) | U.S. Health & Personal Care Stores retail context | U.S.-only, category-level — not global, not L'Oréal-specific |
| Eurostat | `isoc_ec_ib20` | 2020–2025 | Consumer online-purchase adoption (% of individuals, last purchase in 3 months) | All-category online shopping, not beauty-specific spending; structural breaks flagged in parts of the series |
| Eurostat | `isoc_ec_esels` | 2020–2025 | Enterprise B2C web-sales adoption (% of enterprises, 10+ employees) | All-sector, not beauty/retail-specific; France has a flagged break in 2022 |

- FRED series page: **https://fred.stlouisfed.org/series/MRTSSM446USS**
- Eurostat Data Browser: search dataset codes `isoc_ec_ib20` and `isoc_ec_esels` at **https://ec.europa.eu/eurostat/databrowser**

## AI platform documentation

| Source | Supports | Limitation |
|---|---|---|
| OpenAI — Create Campaigns for ChatGPT Ads | Platform-level geographic targeting (country; U.S. state/DMA/ZIP) | Confirms the platform's general capability, not L'Oréal's specific eligible-market assignment |
| OpenAI — Ads in ChatGPT / Measure Results | Platform-level reporting metrics (impressions, clicks, spend, CTR, CPC, CPM, conversions) | Confirms the platform's general reporting capability, not L'Oréal's specific access to those fields |
| OpenAI — Conversion Measurement documentation | Platform-level conversion tracking mechanics | Same distinction as above |

OpenAI Help Center: **https://help.openai.com** · OpenAI Developer docs: **https://developers.openai.com**

## Comparability rule

L'Oréal's own data, compared against itself across years, supports the full quantitative analysis in this project. FRED and Eurostat data are contextual and descriptive only — different geography, different population, or too few comparable observations for a statistical claim. Neither is combined with L'Oréal's figures to produce a derived statistic; they are shown side-by-side, with their limitations stated plainly wherever they appear.

## What is deliberately not included here

Raw source files (the original FRED CSV and Eurostat spreadsheets) and copies of L'Oréal's own annual report PDFs are not redistributed in this repository. They're third-party and company documents, not this project's to rehost — the dataset IDs and links above are enough for anyone to pull the same data directly from the source.
