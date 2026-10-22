# Electronic Business: Idea Validation Lab

Professional retraining program in Electronic Business (BSUIR, Institute of Information Technologies), qualification: Business Analyst-Programmer.

## Goal

Generate business ideas with structured AI-assisted brainstorming, validate them against real search-demand data, and turn the strongest hypotheses into a short stakeholder pitch.

## Author

Yury Kovalenko. Former technical sales, now training as a business analyst.
Course: Electronic Business, 2026.

## Approach

Work is organized in three iterations. Each iteration produces a document that is committed to this repository, so the history shows how the thinking evolved.

| # | Iteration | Focus | Deliverable | Status |
|---|-----------|-------|-------------|--------|
| 1 | Diverge | Problem framing, decomposition, independent idea generation, synthesis | `01-brainstorm/ideas.md` | Planned |
| 2 | Validate | Market boundaries, semantic core, demand data (trend, seasonality, geography) | `02-demand-data/analysis.md` + data tables | Planned |
| 3 | Decide and pitch | Critical review, prioritization, cheap experiments, slides | `03-pitch/pitch.pdf` | Planned |

## Methods

**Ideation (general-purpose, publicly documented methods):**
Blue Ocean Strategy, SCAMPER, Inversion, Cross-industry analogies, First principles, Five Whys, Jobs to Be Done, Morphological analysis, TRIZ (contradiction analysis), Scenario thinking, Red Team / pre-mortem.

**Demand and market analysis:**
- Google Trends: audience interest, trend, seasonality, cycles, regional breakdown.
- Yandex Wordstat: query volume, seasonality, regional demand.
- Market boundary definition and semantic core building.
- Market size estimation with SimilarWeb.
- Time-series reading: trend, seasonality, cycles.

## Combining Google Trends and Yandex Wordstat

Wordstat returns absolute query counts, while Google Trends returns a relative 0-100 index, so the two cannot be added directly. Both series are first normalized to a common scale and then combined using the formula defined in `02-demand-data/method.md`.

## Automation

A small Python script (pandas) will normalize Google Trends and Yandex Wordstat exports and merge them into one table. See `automation/`.

n8n workflows may be added later if a repeatable step appears (for example, pushing results to a spreadsheet).

## Repository structure

- `01-brainstorm/` - raw ideas, synthesis, shortlist
- `02-demand-data/` - queries, exported data, normalization, analysis
- `03-pitch/` - slides for the stakeholder presentation
- `methods/` - short notes on the methods used (own words, no third-party course material)
- `automation/` - Python script for combining demand data

## Data sources and limitations

Data comes from Google Trends and Yandex Wordstat, collected manually on the dates stated in each file. Search demand shows interest, not willingness to pay, so every shortlisted idea is paired with a low-cost validation experiment.

## Note

Educational project. Course-provided materials are intentionally not included in this repository.
