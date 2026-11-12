# Comparative analysis of Import Sourcing and Market Concentration for Petroleum Products in Nigeria

The macroeconomic stability, energy security, and industrial output of Nigeria depend heavily on the continuous importation of petroleum products, notably Premium Motor Spirit (PMS), Gas Oil (AGO), and Dual-Purpose Kerosene (DPK). Despite being a major crude oil exporter, persistent domestic refining capacity limitations have historically forced the nation to rely on external markets to satisfy domestic consumption. While the Dangote Refinery (Lekki, Lagos) reached its 650,000 barrels-per-day design capacity in early 2026, the 2025–2026 data capture a critical transition period where domestic refining was ramping up while commercial imports continued.

This repository contains a rigorous analytical evaluation of Nigeria's petroleum import market across global and intra-African trade corridors for the 2025–2026 period. By analyzing import expenditure values, percentage market shares, Herfindahl-Hirschman Index (HHI) concentration risks, and Pareto distributions, this project establishes a robust data-driven foundation for assessing supply chain vulnerabilities and long-term regional diversification goals under frameworks like the African Continental Free Trade Area (AfCFTA).

## Problem Statement

Nigeria's heavy reliance on imported refined and semi-refined petroleum products exposes its domestic economy to severe external vulnerabilities. These structural challenges manifest across three primary dimensions:

* **Foreign Exchange Volatility:** Heavy demand for foreign currency (such as US Dollars) to settle large-scale fuel import bills exerts sustained downward pressure on the Nigerian Naira, fueling currency depreciation and inflationary pressures.
* **Logistical Vulnerabilities:** Dependence on long-haul maritime shipping exposes domestic supply chains to international freight rate fluctuations, global bunker fuel price volatility, and critical maritime choke points.
* **Acute Market Concentration Risk:** Import sourcing is heavily monopolized by a narrow pool of dominant trading partners. This hyper-concentration leaves domestic energy supplies highly vulnerable to single-source disruptions, sudden geopolitical tensions, and export restrictions imposed by supplying nations.

## Solution

To systematically address these challenges, this project develops a structured, modular Python-based data analytical pipeline. The system ingests raw multi-quarterly Foreign Trade Statistics (FTS) microdata, automates data cleaning and standardisation, filters Harmonized System (HS) Chapter 27 petroleum commodities, computes periodic expenditures, and calculates advanced trade concentration metrics (HHI and Pareto accumulation curves). This enables decision-makers and analysts to objectively evaluate market power distribution and explore regional substitution feasibility

## Importance of the Problem

Energy is the lifeblood of modern economic and social development. When fuel supply chains are unstable, unfordable, or overly concentrated, the negative repercussions cascade across manufacturing, transportation, healthcare, education, and commerce. Energy-sector decisions cannot rely solely on aggregate generation figures; analysts must understand where products come from, who controls the supply, and how vulnerable the nation is to external shocks. Quantifying these concentration risks provides the empirical evidence required to formulate proactive energy policies and foster sustainable domestic and regional refining independence

## Dataset

The project relies on microdata extraction segments spanning six consecutive quarters (Q1 2025 – Q2 2026) sourced from the National Bureau of Statistics (NBS) Foreign Trade Statistics portal:

* **Files Ingested:** Q1_2025_FTS.xlsx through Q2_2026_FTS.xlsx.
* **Sheets Extracted:** TABLE 4 and TABLE 5C detailing partner-specific trade and product classifications.
* **Dataset Partitioning:** The data are bifurcated into a Global Petroleum Imports Dataset (capturing major international suppliers like the US, Netherlands, India, and UAE) and an Intra-African Trade Dataset (capturing continental partners like Angola, Togo, Ghana, and Libya).

### Dataset Dictionary

<table border="1" cellpadding="8" cellspacing="0">
  <thead>
    <tr style="background-color: #f2f2f2;">
      <th>Field</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Code</code></td>
      <td>String</td>
      <td>Two-letter international standard country code representing partner origin (e.g., 'US', 'IN', 'NL')[cite: 9].</td>
    </tr>
    <tr>
      <td><code>Country of Origin</code></td>
      <td>String</td>
      <td>Standardized name of the trading partner country (e.g., 'The United States of America', 'India')[cite: 9].</td>
    </tr>
    <tr>
      <td><code>HS Code</code></td>
      <td>String</td>
      <td>Harmonized System commodity classification code, filtered for Chapter 27 (e.g., '2709000000', '2710192100')[cite: 9].</td>
    </tr>
    <tr>
      <td><code>Products Description</code></td>
      <td>String</td>
      <td>Official descriptive text of the petroleum commodity imported (e.g., 'Petroleum and Bituminous oils', 'Gas oil')[cite: 9].</td>
    </tr>
    <tr>
      <td><code>Import Value (Million Naira)</code></td>
      <td>Float64</td>
      <td>Monetary expenditure value of the imported product expressed in millions of Nigerian Naira[cite: 9].</td>
    </tr>
    <tr>
      <td><code>Quarter</code></td>
      <td>String</td>
      <td>Temporal quarterly identifier ('Q1', 'Q2', 'Q3', 'Q4')[cite: 10].</td>
    </tr>
    <tr>
      <td><code>Year</code></td>
      <td>Integer</td>
      <td>Calendar year of the import record (2025, 2026)[cite: 10].</td>
    </tr>
  </tbody>
</table>

---


