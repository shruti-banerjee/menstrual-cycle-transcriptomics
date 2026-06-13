# Menstrual Cycle Transcriptomics — Gene Expression Across Cycle Phases

### Computational Biology Internship Project | June 2025

**Author:** Shruti Banerjee  
**Tools:** R · tidyverse · GEOquery · ggplot2  
**Data Source:** NCBI GEO — GSE7305

---

## Overview

In April 2026, Riishede et al. (*Nature Medicine*) mapped nearly 3,000 proteins across the menstrual cycle and found that **198 proteins fluctuate in synchronized patterns throughout the month** — touching immune function, metabolism, cardiovascular regulation, and neurological signalling.

Their finding raised an immediate upstream question:

> **What is happening at the gene expression level that drives these protein fluctuations?**

This project investigates exactly that — using publicly available transcriptomic data to identify differentially expressed genes across menstrual cycle phases and map the biological pathways involved.

Proteins tell us *what* changed. Genes tell us *why.*

---

## Background & Clinical Relevance

The menstrual cycle is not a reproductive side event — it is a **whole-body biological rhythm**. Yet most clinical drug dosing treats the female body as biologically static throughout the month.

If immune regulators, metabolic enzymes, and vascular signalling molecules fluctuate rhythmically, then a woman's response to medication may differ between week 1 and week 3. This has implications for:

- Antidepressants and ADHD medications
- Pain management and anaesthesia
- Oncology drugs and immunotherapies
- Cardiovascular treatments and vaccines

This project is a contribution toward **sex-aware, phase-aware precision medicine.**

---

## Dataset

| Parameter | Detail |
|---|---|
| **GEO Accession** | GSE7305 |
| **Organism** | *Homo sapiens* |
| **Tissue** | Endometrium |
| **Platform** | Affymetrix Human Genome U133 Plus 2.0 |
| **Cycle Phases** | Follicular · Ovulatory · Luteal |
| **Access** | Programmatic via GEOquery — no manual download required |

---

## Pipeline

```
Raw Expression Data (NCBI GEO — GSE7305)
        ↓
Data Import (GEOquery)
        ↓
Metadata Extraction & Phase Labelling (dplyr)
        ↓
Data Cleaning & Normalisation (tidyr, mutate())
        ↓
Exploratory Data Analysis (ggplot2)
        ↓
Differential Expression by Cycle Phase
        ↓
Visualisation — Heatmap · Volcano Plot · Expression Timeline
        ↓
Biological Interpretation
```

---

## Tools & Technologies

**Data Access & Wrangling**

![GEOquery](https://img.shields.io/badge/GEOquery-Bioconductor-brightgreen?style=flat)
![dplyr](https://img.shields.io/badge/dplyr-tidyverse-blue?style=flat)
![tidyr](https://img.shields.io/badge/tidyr-tidyverse-blue?style=flat)
![readr](https://img.shields.io/badge/readr-tidyverse-blue?style=flat)

**Visualisation**

![ggplot2](https://img.shields.io/badge/ggplot2-R-276DC3?style=flat)
![stringr](https://img.shields.io/badge/stringr-tidyverse-blue?style=flat)

**Environment**

![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google_Colab-cloud-orange?style=flat)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)

**Database**

![NCBI GEO](https://img.shields.io/badge/NCBI-GEO-red?style=flat)

---

## Results

*(Updating as analysis progresses)*

### Differentially Expressed Genes

| Comparison | DEGs Identified | Upregulated | Downregulated |
|---|---|---|---|
| Follicular vs Luteal | — | — | — |
| Follicular vs Ovulatory | — | — | — |
| Luteal vs Ovulatory | — | — | — |

### Top Cycling Genes

| Gene | Phase Pattern | Biological Function |
|---|---|---|
| — | — | — |

---

## Visualisations

*(Charts will be added as analysis progresses)*

### Gene Expression Heatmap
> Expression levels of top variable genes across cycle phases

### Volcano Plot
> Differentially expressed genes — fold change vs statistical significance

### Expression Timeline
> Top cycling genes plotted across follicular → ovulatory → luteal phases

---

## Repository Structure

```
menstrual-cycle-transcriptomics/
│
├── README.md
├── scripts/
│   ├── 01_data_import.R
│   ├── 02_preprocessing.R
│   ├── 03_eda.R
│   └── 04_visualization.R
└── figures/
    └── (output plots)
```

---

## How to Reproduce

**In Google Colab (R):**

```r
%%R
install.packages("BiocManager")
BiocManager::install("GEOquery")
library(GEOquery)
library(tidyverse)

gse <- getGEO("GSE7305", GSEMatrix = TRUE)
```

**In R / RStudio:**

```r
install.packages("BiocManager")
BiocManager::install("GEOquery")
library(GEOquery)
library(tidyverse)

gse <- getGEO("GSE7305", GSEMatrix = TRUE)
```

---

## Reference

Riishede I et al. *Plasma proteomic signature of the human menstrual cycle.* Nature Medicine. April 13, 2026. doi:10.1038/s41591-026-04326-5

---

## Key Biological Question

This project sits upstream of the Riishede et al. findings. Where their proteomics work reveals *what* fluctuates, transcriptomics reveals *what is driving it* — the gene regulatory architecture behind the monthly biological shift.

Understanding this layer is essential for moving medicine from population-level averages toward **phase-aware, sex-informed treatment.**

---

**Shruti Banerjee** · [banerjee.shruti1306@gmail.com](mailto:banerjee.shruti1306@gmail.com) · [GitHub](https://github.com/shruti-banerjee)

*Developed as part of a Computational Biology internship — June 2025.*
