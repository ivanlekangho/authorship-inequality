# Who Is Running the Lab?
### Authorship Inequality in International Scientific Collaboration
**DATASCI 112 — Stanford University, Winter 2026**  
*Savya Meattle & Ivan Ho*

---

## Overview

Last authorship in a scientific paper signals the Principal Investigator — the person who leads the lab, controls the funding, and gets the credit that drives hiring and grant decisions. This project asks a simple question: do Global South researchers receive last-authorship credit proportional to their presence on international research teams?

Using 14,250 internationally co-authored papers across 19 scientific disciplines (2005–2023), we find a statistically significant deficit of **−8.9%** — Global South researchers are 8.9 percentage points less likely to hold the last-author slot than their team presence would predict. This gap holds across all fields, all citation quartiles, and has not closed in 18 years.

---

## Key Findings

- **The gap exists:** GS researchers comprise 45.4% of teams on average, but are 19% more likely to appear as first author than last author (p < 0.0001)
- **It is everywhere:** The deficit is present in 18 of 19 fields studied
- **18 years, no progress:** Year-by-year analysis from 2005–2023 shows a flat trend — open-science initiatives have produced no measurable change
- **It is not about prestige:** The deficit is nearly identical across all four citation quartiles — high-impact papers show the same pattern as low-impact ones

---

## Data Sources

| Source | What it provides |
|---|---|
| [OpenAlex API](https://openalex.org) | Paper metadata, author affiliations, institution countries, citation counts |
| [World Bank API](https://datahelpdesk.worldbank.org/knowledgebase/articles/906519) | Country classification into Global South / Global North |

**Dataset:** 14,250 papers, 111,602 author-paper rows, 180 countries  
**Inclusion criteria:** ≥1 GS and ≥1 GN author with known institutional country, team size 2–15, ≥2 distinct nationalities

---

## Estimand

For each paper, we calculated the probability that the last author is from the Global South, then subtracted the share of Global South researchers on that paper's team.

> A deficit of −8.9% means GS researchers are 8.9 percentage points less likely to hold the last-author slot than their team presence would predict.

---

## Repository Structure

```
├── README.md
├── LICENSE
├── .gitignore
├── Final_Project_Savya_and_Ivan.ipynb   # full analysis notebook
├── DATASCI_112_Project_Poster.pdf       # poster presented at class
└── figures/                             # saved visualizations
```

---

## How to Run

1. Clone the repo
```bash
git clone https://github.com/yourusername/authorship-inequality-global-south.git
```

2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn requests
```

3. Run the notebook top to bottom  
   Note: raw data is not included in this repo. To reproduce the data collection step, you will need free API access to [OpenAlex](https://openalex.org) and the [World Bank API](https://api.worldbank.org). No API key is required for either.

---

## Limitations

- The Global South / Global North binary simplifies complex institutional realities — countries like China, Brazil, and India are structurally very different from lower-income GS countries but are classified together
- Last authorship is a useful proxy for senior leadership but does not perfectly capture contribution, decision-making power, or PI status
- OpenAlex institutional country data has some missing values; papers with unknown author affiliations were excluded

---

## Citation

If you use this work, please cite:

```
Meattle, S. & Ho, I. (2026). Who Is Running the Lab? Authorship Inequality 
in International Scientific Collaboration. DATASCI 112, Stanford University.
```

---

## License

MIT License — see `LICENSE` for details.
