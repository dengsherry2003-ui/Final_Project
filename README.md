# Loyalty Signaling in Hong Kong: A Textual Analysis of Political Discourse from 1997 to 2026

## Overview

This project investigates the evolution of "loyalty signaling" discursive practices by successive Chief Executives (CEs) of the Hong Kong Special Administrative Region (HKSAR) toward the PRC central authorities  from 1997 to 2026. Taking an empirical and quantitative approach to political discourse analysis, this study maps how political alignment is communicated during times of socio-political friction, providing a novel metric to evaluate central-local governmental relations inside Hong Kong under the "One Country, Two Systems" framework.

The project collects, curates, and utilizes a comprehensive database of public addresses and press releases spanning five CE administrations (Tung Chee-hwa, Donald Tsang, Leung Chun-ying, Carrie Lam, and John Lee), alongside corresponding statements from mainland officials.

## Data Sources

The project relies on public records and official text archives fetched directly from HKSAR and Central Government portals:

- **CE Public Speeches & Articles**: Stored in `Data/Data_Raw/Speeches_and_Articles/`, this corpus covers the public addresses directly delivered by the five Chief Executives, sourced from their official archive websites.
- **CE Office Press Releases**: Stored in `Data/Data_Raw/Press_Release/`, these officially issued press summaries provide an alternative, more bureaucratic communication channel.
- **Central Authority HK-related Speeches**: Stored in `Data/Data_Raw/Central/Liaison_Office/`, this includes policy-focused releases and central leaders' public speeches regarding Hong Kong affairs.
- **Five-Year Plans**: Stored in `Data/Data_Raw/Five-Year_Plan/`, these are manually compiled national blueprints released by the CPG since 1997, utilized as part of the broader national strategic discourse.

## Methodology

To measure loyalty signaling effectively, the project executed the following computational workflow via Python (`Code/` folder):

1. **Keyword Compilation**: We categorized known loyalty-signaling terms into three layers (Authority, Strategic Alignment, Cognitive Convergence) encompassing six distinct types (Personal, Institutional, Policy, Nationalistic, Ideological, and Rhetorical loyalty).
2. **Text Normalization & Keyword Density**: Through robust Chinese Natural Language Processing (via `jieba` and regular expressions), we evaluated the raw text and calculated a standardized metric: *Loyalty Signaling Keyword Density* (frequency of keyword hits per 10,000 characters) across the corpus.
3. **Cosine Similarity Analysis (TF-IDF)**: Using the Term Frequency-Inverse Document Frequency (TF-IDF) algorithm, we transformed unstructured CE speeches and central leader addresses into high-dimensional vectors to calculate their *Cosine Similarity*, tracking the degree to which CE rhetoric strictly converges with the Mainland's specific "officialese" patterns.

## Key Findings

- **Cyclical and Reparative Signaling**: Loyalty signaling generally spikes after socio-political friction. Signaling densities rose remarkably post the 2014 Umbrella Movement and the 2019 Anti-Extradition Bill Movement. Under the latter administrations (Carrie Lam and John Lee), loyalty signaling became a standardized and consistent pillar of executive discourse.
- **"Modular" Compliance Over Wholesale Assimilation**: The data refutes the possibility of an immediate "Mainlandization" of language. Instead of a wholesale adoption of generalized mainland bureaucratic jargon, recent CEs employed a "modular" rhetorical strategy—inserting targeted loyalty keywords (like "national security" and "patriots administering Hong Kong") heavily while maintaining the pragmatic and technocratic phrasing inherent to Hong Kong administration.
- **Medium Shifting**: In 2026, John Lee's administration exhibited an inversion in signaling medium—expressing measurably more loyalty through bureaucratic press releases than through primary speeches. This transition implies systemic institutionalization of political alignment, allowing the CE's public and verbal addresses to return somewhat to pragmatic and economic themes.

## Limitations

- **"Front-Stage" Constraint**: Our dataset isolates publicly available text. This inherently limits our observations to public positioning, missing the nuances of private ("back-stage") interactions.
- **Loss of Pragmatic/Linguistic Nuance**: The density metrics and similarity computations are powerful macro-level identifiers but may sometimes overlook rhetorical tone, coded metaphors, or context-specific double-meanings.
- **Monolingual Focus**: The focus on Chinese-language text neglects Hong Kong's English-language messaging strategies regarding the international commercial audience.

## Project Structure

```text
Final_Project-main/
├── Code/                          # The analytical engine of the project
│   ├── Analysis_combined.ipynb    # Main script: visualizes/generates keyword densities and cosine similarities
│   ├── Central.ipynb              # Fetches and cleans CPG speeches and remarks
│   ├── Press_Release.ipynb        # Scrapes press summaries from successive CEs
│   ├── Speeches_and_Articles.ipynb# Scrapes public speeches/articles for the five CEs
│   └── keywords.ipynb             # Structured mapping of 6-dimension loyalty keywords
├── Data/                          # All ingested and scraped raw assets
│   └── Data_Raw/
│       ├── Central/               # Central leadership output & Liaison office press docs
│       ├── Five-Year_Plan/        # CPG's five-year plans since 1997 
│       ├── Press_Release/         # Summaries divided by CE term (Lam, Tsang, Lee, etc.)
│       └── Speeches_and_Articles/ # Direct speeches divided by CE term
├── docs/                          # GitHub Pages host directory
│   ├── index.html                 # Main landing HTML dashboard
│   ├── QRcode.html                # QR code utility for report access
│   └── report.pdf                 # Live published PDF of the final result
├── Report/                        # Outputs and deliverables
│   ├── Graphs/                    # Raw generated charts, scatterplots, heatmaps
│   ├── Poster/                    # Slidedeck for formatting the 2-minute presentation
│   └── Template/                  # LaTeX generation directory (rho-class, .tex code, bibliography, generated figures)
├── .vscode/                       # Editor-specific settings
├── .gitignore                     # Git tracking exclusions
├── GITHUB_PAGES.md                # Deployment tracking info
└── README.md                      # This project overview document
```

## How to View and Run

You can explore our interactive artifacts and report online:

- **GitHub repository**: [https://github.com/dengsherry2003-ui/Final_Project/tree/main#](https://github.com/dengsherry2003-ui/Final_Project/tree/main#)
- **Live webpage report**: [https://dengsherry2003-ui.github.io/Final_Project/](https://dengsherry2003-ui.github.io/Final_Project/)
- **Poster**: `Report/Poster/Poster.pdf/`

If you seek to run or compile the LaTeX project locally, utilize the pre-configured VS Code tasks:

- `Compile LaTeX (xelatex)` — Regenerates `report.pdf` within the `Report/Template` framework.
- `Compile LaTeX and Update HTML` — Generates and updates the public-facing `docs/report.pdf` file.

To re-run the Python analyses locally, ensure your environment supports `jupyter`, `jieba`, and relevant data science libraries (like `pandas`, `sklearn`, and plotting tools). Run the scrapers (`Central.ipynb`, etc.) for any data updates before executing the central `Analysis_combined.ipynb` script.

## Authors

* **Xinran Deng** (The University of Hong Kong)
* **Jingyi Liu** (The University of Hong Kong)
* **Jingquan Zhong** (The University of Hong Kong)

Course: POLI3148 | Spring 2026
