# Who Is Running the Lab?
### Authorship Inequality in International Scientific Collaboration
**Stanford University, DATASCI 112 — Winter 2026**  
*Savya Meattle & Ivan Ho*

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-lightblue)
![OpenAlex](https://img.shields.io/badge/Data-OpenAlex%20API-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## Overview

Last authorship in a scientific paper signals the Principal Investigator — the person who leads the lab, controls the funding, and gets the credit that drives hiring and grant decisions. This project asks: **do Global South researchers receive last-authorship credit proportional to their presence on international research teams?**

Using **14,250 internationally co-authored papers** across 19 scientific disciplines (2005–2023), we find a statistically significant deficit of **−8.9%** — Global South researchers are 8.9 percentage points less likely to hold the last-author slot than their team presence would predict. This gap holds across all fields, all citation quartiles, and **has not closed in 18 years**.

---

## Technical Skills Demonstrated

| Area | Details |
|---|---|
| **Data Collection** | REST API integration (OpenAlex, World Bank), pagination, rate-limit handling, JSON parsing |
| **Data Engineering** | Multi-source dataset construction, entity resolution across 180 countries, author-level record linkage across 111,602 rows |
| **Statistical Analysis** | Hypothesis testing (McNemar's test), confidence intervals, longitudinal trend analysis, subgroup analysis across 19 fields and 4 citation quartiles |
| **Data Visualization** | Choropleth world maps, forest plots with confidence intervals, time-series with trend overlays, grouped bar charts |
| **Python Libraries** | `pandas`, `numpy`, `matplotlib`, `seaborn`, `requests`, `scipy` |

---

## Key Findings

- **The gap exists:** GS researchers comprise 45.4% of teams on average, but are 19% more likely to appear as first author than last (p < 0.0001)
- **It is everywhere:** The deficit is present in 18 of 19 fields studied
- **18 years, no progress:** Year-by-year analysis (2005–2023) shows a completely flat trend — open-science initiatives have produced no measurable change
- **It is not about prestige:** The deficit is nearly identical across all four citation quartiles — the pattern holds whether the paper has 0 or 500+ citations

---

## Dataset

| Property | Value |
|---|---|
| Papers | 14,250 |
| Author-paper rows | 111,602 |
| Countries | 180 |
| Fields | 19 |
| Time window | 2005–2023 |
| Sources | OpenAlex API + World Bank API |

**Inclusion criteria:** ≥1 Global South and ≥1 Global North author with known institutional country, team size 2–15, ≥2 distinct nationalities.

---

## Estimand

For each paper, we calculated the probability that the last author is from the Global South, then subtracted the share of Global South researchers on that paper's team.

> A deficit of −8.9% means GS researchers are 8.9 percentage points less likely to hold the last-author slot than their team presence would predict.

This operationalization allows apples-to-apples comparison across fields and team sizes of different compositions.

---

## Repository Structure

```
├── README.md
├── LICENSE
├── Authorship_Inequality_Code.ipynb     # full analysis — data collection through visualization
├── Authorship_Inequality_Poster.pdf     # final research poster
└── figures/                             # all saved visualizations (PNG, 300dpi)
```

---

## How to Run

1. Clone the repo
```bash
git clone https://github.com/yourusername/authorship-inequality-global-south.git
cd authorship-inequality-global-south
```

2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn requests scipy
```

3. Run the notebook top to bottom

> **Note:** Raw data is not included in this repo. To reproduce the data collection step, you will need free API access to [OpenAlex](https://openalex.org) and the [World Bank API](https://api.worldbank.org). No API key is required for either.

---

## Limitations

- The Global South / Global North binary simplifies complex institutional realities — China, Brazil, and India are classified alongside lower-income GS countries despite very different research ecosystems
- Last authorship is a useful proxy for PI status but does not perfectly capture contribution or decision-making power
- OpenAlex institutional country data has some missing values; papers with unknown author affiliations were excluded

---

## Citation

```
Meattle, S. & Ho, I. (2026). Who Is Running the Lab? Authorship Inequality 
in International Scientific Collaboration. DATASCI 112, Stanford University.
```

---

## License

MIT License — see `LICENSE` for details.
