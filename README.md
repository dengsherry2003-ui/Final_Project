# Hong Kong Chief Executive Discourse Analysis: A Temporal Study of Loyalty Signaling from 1997 to 2026

## Overview
This repository contains the code and data analysis pipeline for a longitudinal study of Hong Kong Chief Executives' (CE) public discourse. The project focuses on tracking "loyalty-signaling" rhetoric over time by analyzing the frequency of specific keywords in CE speeches and press releases, as well as measuring textual similarity between CE communications and HK-related speeches by central state leaders.

## Repository Structure

The project is divided into data collection, keyword definition, and analytical modeling. The Jupyter notebooks are located in the `Code/` directory and should generally be explored in the following order:

### 1. Data Collection & Processing
*   **`Code/Speeches_and_Articles.ipynb`** 
    Scrapes, collects, and pre-processes the official speeches and published articles directly from the Chief Executive's website.
*   **`Code/Press_Release.ipynb`**
    Scrapes, collects, and pre-processes the official government press releases from the Chief Executive's website.

### 2. Dictionaries & Parameters
*   **`keywords.ipynb`**
    Contains the methodological framework and lists of the specific "loyalty-signaling" keywords used to measure political alignment in the text bodies. 

### 3. Analysis & Visualization
*   **`Code/Analysis_combined.ipynb`**
    The core analytical notebook. It merges the speech and press release datasets, applies the keyword dictionaries, and generates the data visualizations tracking the density and distribution of loyalty signaling over different CE administrations.
*   **`Code/Central.ipynb`**
    Conducts comparative text analysis. This notebook measures the semantic similarity between the CEs' discourse and HK-related speeches delivered by central state leaders.

## Usage
To reproduce the analysis, it is recommended to run the notebooks in the following sequence:
1. Run the collection notebooks (`Press_Release.ipynb` and `Speeches_and_Articles.ipynb`) to gather the raw text data.
2. Ensure `keywords.ipynb` is configured with your desired search terms.
3. Run `Analysis_combined.ipynb` and `Central.ipynb` to generate the statistical outputs and visualizations.

***

Let me know if you want to add sections for prerequisites (like Python versions or specific NLP libraries like `nltk`, `spacy`, or `jieba`) or instructions on how to install dependencies!
