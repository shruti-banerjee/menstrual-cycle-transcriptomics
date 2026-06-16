# Menstrual Cycle Transcriptomics Pipeline

### Computational Biology Internship Project | NexoraGroup | June 2026

**Author:** Shruti Banerjee  
**Tools:** R · tidyverse · GEOquery · ggplot2  
**Data Source:** NCBI GEO — GSE7305

---

## Overview

In April 2026, Riishede et al. (*Nature Medicine*) mapped nearly 3,000 proteins across the menstrual cycle and found that **198 proteins fluctuate in synchronized patterns throughout the month** — touching immune function, metabolism, cardiovascular regulation, and neurological signalling.

Their finding raised two immediate questions:

> **What is happening at the gene expression level that drives these protein fluctuations?**
> **And why hasn't anyone built a clean, reproducible pipeline to investigate it?**

This project does both.

It is simultaneously a **transcriptomic analysis** of gene expression across menstrual cycle phases and a **modular, reusable R pipeline** that can be pointed at any GEO dataset by changing a single configuration file.

Proteins tell us *what* changed. Genes tell us *why.*  
And a good pipeline means anyone can ask the same question — for any condition, any tissue, any dataset.

---

## Background & Clinical Relevance

The menstrual cycle is not a reproductive side event — it is a **whole-body biological rhythm.** Yet most clinical drug dosing treats the female body as biologically static throughout the month.

If 198 proteins fluctuate rhythmically — including immune regulators, metabolic enzymes, and vascular signalling molecules — then a woman's response to medication may differ between week 1 and week 3. This has implications for:

- Antidepressants and ADHD medications
- Pain management and anaesthesia
- Oncology drugs and immunotherapies
- Cardiovascular treatments and vaccines

This project contributes toward **sex-aware, phase-aware precision medicine** — and toward making that research accessible and reproducible.

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

## Pipeline Architecture

```
config.R  ←  Change dataset, phases, or thresholds here
    ↓
01_data_import.R      — Pull any GEO dataset programmatically
    ↓
02_preprocess.R       — Clean metadata, label phases, normalise
    ↓
03_eda.R              — Exploratory analysis, distributions, QC
    ↓
04_visualize.R        — Publication-ready figures
    ↓
figures/ + outputs/   — All results saved automatically
```

> **Engineer note:** The entire pipeline is driven by `config.R`. Swap the GEO accession number and re-run — the pipeline adapts. No hardcoded values anywhere in the analysis scripts.

---

## Tools & Technologies

**Data Access & Wrangling**

![GEOquery](https://img.shields.io/badge/GEOquery-Bioconductor-brightgreen?style=flat)
![dplyr](https://img.shields.io/badge/dplyr-tidyverse-blue?style=flat)
![tidyr](https://img.shields.io/badge/tidyr-tidyverse-blue?style=flat)
![readr](https://img.shields.io/badge/readr-tidyverse-blue?style=flat)
![stringr](https://img.shields.io/badge/stringr-tidyverse-blue?style=flat)

**Visualisation**

![ggplot2](https://img.shields.io/badge/ggplot2-R-276DC3?style=flat)

**Environment**

![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google_Colab-cloud-orange?style=flat)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)

**Database**

![NCBI GEO](https://img.shields.io/badge/NCBI-GEO-red?style=flat)

---

## Repository Structure

```
menstrual-cycle-transcriptomics/
│
├── README.md
├── config.R                  ← dataset ID, phase labels, thresholds
├── scripts/
│   ├── 01_data_import.R      ← GEOquery pull + raw data export
│   ├── 02_preprocess.R       ← cleaning, normalisation, phase labelling
│   ├── 03_eda.R              ← exploratory analysis + QC plots
│   └── 04_visualize.R        ← heatmap, volcano plot, timeline
├── functions/
│   └── utils.R               ← reusable helper functions
├── figures/                  ← all output plots saved here
└── outputs/                  ← results tables saved here
```

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
> Expression levels of top variable genes across all samples, grouped by cycle phase

### Volcano Plot
> Differentially expressed genes — fold change vs statistical significance

### Expression Timeline
> Top cycling genes plotted across follicular → ovulatory → luteal phases

---

## How to Reproduce

**Step 1 — Clone the repo**
```
git clone https://github.com/shruti-banerjee/menstrual-cycle-transcriptomics
```

**Step 2 — Open `config.R` and set your parameters**
```r
GEO_ID        <- "GSE7305"       # swap for any GEO dataset
PHASE_COL     <- "cycle phase"   # metadata column name
PHASES        <- c("follicular", "ovulatory", "luteal")
PVAL_CUTOFF   <- 0.05
FC_CUTOFF     <- 1.5
```

**Step 3 — Run scripts in order**
```r
source("scripts/01_data_import.R")
source("scripts/02_preprocess.R")
source("scripts/03_eda.R")
source("scripts/04_visualize.R")
```

**In Google Colab (R):**
```
%%R
# Run config first, then source each script
source("config.R")
source("scripts/01_data_import.R")
```

---

## Scientific Questions This Project Addresses

This project is designed to be extended. Beyond the primary analysis, the pipeline can be reused to investigate:

- **Immune regulation** — which immune genes are suppressed in the luteal phase, and does this explain cycle-linked autoimmune flares?
- **Drug metabolism** — do CYP enzyme genes fluctuate across phases, meaning drug dosing hits differently week to week?
- **Disease risk** — do genes linked to endometriosis or PCOS show phase-specific expression in healthy tissue?
- **Mental health** — which neurological signalling genes change across the cycle, and could this explain cycle-linked depression and anxiety?

---

## Reference

Riishede I et al. *Plasma proteomic signature of the human menstrual cycle.* Nature Medicine. April 13, 2026. doi:10.1038/s41591-026-04326-5

---

## End-to-End Project Journey

This project is built as a complete, documented analysis — from raw public data to biological conclusions. Every step is traceable, reproducible, and interpretable.

```
RAW DATA                   publicly available expression matrix (NCBI GEO)
    ↓
CLEANING                   metadata extraction, phase labelling, normalisation
    ↓
ANALYSIS                   differential expression across cycle phases
    ↓
VISUALISATION              heatmap · volcano plot · expression timeline
    ↓
BIOLOGICAL CONCLUSION      which genes drive cyclic change — and what does that mean clinically?
```

No black boxes. No skipped steps. Anyone can follow this from start to finish.

---

## What This Project Demonstrates

| Skill Area | Evidence |
|---|---|
| **Bioinformatics Analysis** | End-to-end transcriptomic workflow on real clinical data |
| **Pipeline Engineering** | Modular, config-driven, reusable across any GEO dataset |
| **Data Wrangling** | tidyverse — dplyr, tidyr, stringr, readr |
| **Visualisation** | Publication-ready ggplot2 figures |
| **Reproducible Research** | Fully documented, version-controlled, open source |
| **Biological Interpretation** | Findings connected to clinical relevance and existing literature |

---

## About This Project

Built during a **Computational Biology internship at NexoraGroup** as an independent portfolio project. Motivated by a 2026 Nature Medicine paper and the absence of a clean, open-source transcriptomic pipeline investigating the same question at the gene level.

---

**Shruti Banerjee** · [banerjee.shruti1306@gmail.com](mailto:banerjee.shruti1306@gmail.com) · [GitHub](https://github.com/shruti-banerjee)
