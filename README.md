
# 🧬 # The Cycle Code
### *A transcriptomic investigation into the most overlooked rhythm in human biology*

---

> *In April 2026, a paper dropped in Nature Medicine that should have been front page news.*
> *198 proteins. Fluctuating. Synchronized. Every single month.*
> *The female body is not static. It never was.*
> *So I asked the next question nobody was asking:*
> **What is happening at the gene level that drives all of this?**

---



For decades, medical research has treated the female body as a stable system — one set of values, one standard dose, one biological baseline.

That assumption just got shattered.

Riishede et al. (Nature Medicine, 2026) mapped nearly 3,000 proteins across the menstrual cycle and found that 198 of them fluctuate in coordinated, rhythmic patterns every month — touching immune function, metabolism, cardiovascular regulation, neurological signaling, and more.

The menstrual cycle isn't a reproductive event.  
**It's a whole-body biological conductor.**

Their work answered *what* changes.  
This project goes upstream to answer ***why.***

---



Proteins don't appear from nowhere. They are built from instructions — genes that switch on and off, turn loud and quiet, in patterns we are only beginning to decode.

This project uses publicly available transcriptomic data (NCBI GEO: GSE7305) to map gene expression across menstrual cycle phases in human endometrial tissue. Built entirely in R using the tidyverse ecosystem — clean, reproducible, and open source.

The question driving every line of code:

> *Which genes are orchestrating the monthly biological shift — and what do they tell us about disease, drug response, and precision medicine?*

---

## The Stack

| Layer | Tool |
|---|---|
| Data Access | GEOquery |
| Wrangling | dplyr, tidyr, readr |
| Feature Engineering | mutate(), case_when() |
| Visualization | ggplot2 |
| Environment | R / Google Colab |
| Data Source | NCBI GEO — GSE7305 |

---

## The Pipeline

```
📥  Pull raw expression data from NCBI GEO
        ↓
🧹  Clean metadata — label cycle phases, remove noise  
        ↓
🔍  Exploratory analysis — distributions, outliers, patterns
        ↓
📊  Differential expression — which genes change between phases?
        ↓
🌋  Visualize — heatmaps, volcano plots, expression timelines
        ↓
🧠  Interpret — what biology do these genes point to?
```

---

## The Visualizations

*(Updating as analysis progresses)*

- 🌋 **Volcano plot** — significant genes across cycle phases
- 🔥 **Heatmap** — expression landscape across all samples
- 📈 **Timeline plot** — top cycling genes across phases
- 🔬 **Pathway summary** — what biological systems are involved

---

## The Bigger Picture

If 198 proteins shift rhythmically every month — including immune regulators, vascular signaling molecules, and metabolic enzymes — then a woman's response to antidepressants, pain medication, chemotherapy, or anesthesia may not be the same in week 1 as it is in week 3.

Most clinical trials still don't account for this.  
Most drug dosing protocols don't either.

**This project is a small contribution to changing that.**

---

## Reference

Riishede I et al. *Plasma proteomic signature of the human menstrual cycle.* Nature Medicine. April 13, 2026.  
doi:10.1038/s41591-026-04326-5

---

## Author

**Shruti Banerjee**  
MSc Bioinformatics — Transcriptomics & Computational Biology  
[GitHub](https://github.com/shruti-banerjee) • [LinkedIn](https://linkedin.com/in/shruti-banerjee)

---

*Built during a Computational Biology internship. Driven by curiosity about what we still don't know about female biology.*
