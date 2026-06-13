# menstrual-cycle-transcriptomics
Transcriptomic analysis of gene expression across menstrual cycle phases using R and tidyverse — inspired by Riishede et al. 2026

# 🧬 Menstrual Cycle Transcriptomics
### *What drives the proteins? A gene expression investigation.*

---

## The Motivation

In April 2026, Riishede et al. published a landmark study in *Nature Medicine* showing that **198 proteins fluctuate in synchronized patterns across the menstrual cycle** — affecting immune function, metabolism, cardiovascular regulation, and neurological signaling.

Their finding raised an immediate upstream question:

> **What is happening at the gene expression level that drives these protein fluctuations?**

This project investigates exactly that — using publicly available transcriptomic data to map which genes are differentially expressed across menstrual cycle phases, and what biological pathways they belong to.

Proteins tell us *what* changed. Genes tell us *why*.

---

## Project Overview

| Item | Detail |
|---|---|
| **Data Source** | NCBI GEO — GSE7305 |
| **Organism** | *Homo sapiens* |
| **Tissue** | Endometrium |
| **Cycle Phases** | Follicular, Ovulatory, Luteal |
| **Tools** | R, tidyverse, GEOquery, ggplot2 |
| **Analysis Type** | Exploratory transcriptomic analysis + visualization |

---

## Why This Matters Clinically

The menstrual cycle is not a reproductive side feature — it is a **whole-body biological rhythm**. Yet most drugs are dosed as though female biology is static throughout the month.

This has implications for:
- Antidepressants and ADHD medications
- Pain management
- Oncology drugs and immunotherapies
- Cardiovascular treatments

Understanding the transcriptomic architecture behind cyclic biology is a step toward **sex-aware, phase-aware precision medicine**.

---

## Pipeline

```
GEO Data (GSE7305)
        ↓
   Data Import (GEOquery)
        ↓
   Cleaning & Preprocessing (tidyverse)
        ↓
   Exploratory Data Analysis (dplyr, ggplot2)
        ↓
   Differential Expression (by cycle phase)
        ↓
   Visualization (ggplot2 — heatmap, volcano plot, expression timeline)
        ↓
   Biological Interpretation
```

---

## Visualizations

*(Coming soon — plots will be added as analysis progresses)*

- 📊 Gene expression heatmap across cycle phases
- 🌋 Volcano plot of differentially expressed genes
- 📈 Expression timeline of top cycling genes
- 🔬 Pathway enrichment summary

---

## Repository Structure

```
menstrual-cycle-transcriptomics/
│
├── README.md
├── data/
│   └── (GEO data — loaded programmatically, not stored here)
├── scripts/
│   ├── 01_data_import.R
│   ├── 02_preprocessing.R
│   ├── 03_eda.R
│   └── 04_visualization.R
└── figures/
    └── (output plots)
```

---

## Tools & Packages

- **R** — primary analysis language
- **GEOquery** — programmatic access to NCBI GEO datasets
- **tidyverse** — data wrangling (dplyr, tidyr, readr)
- **ggplot2** — publication-quality visualizations
- **stringr** — string manipulation for metadata cleaning

---

## Reference

Riishede I et al. *Plasma proteomic signature of the human menstrual cycle.* Nature Medicine. April 13, 2026. doi:10.1038/s41591-026-04326-5

---

## Author

**Shruti Banerjee**
MSc Bioinformatics | Transcriptomics & Computational Biology
[GitHub](https://github.com/shruti-banerjee) • [LinkedIn](https://linkedin.com/in/shruti-banerjee)

---

*This project was developed as part of a Computational Biology internship and independent portfolio work.*
