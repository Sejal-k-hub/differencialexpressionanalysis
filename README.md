# 🧬 miRNA-DE-multiMiR

<p align="center">
  <img src="https://img.shields.io/badge/R-4.3%2B-blue?style=flat-square&logo=r" />
  <img src="https://img.shields.io/badge/edgeR-Differential%20Expression-green?style=flat-square" />
  <img src="https://img.shields.io/badge/multiMiR-miRNA%20Target%20Validation-purple?style=flat-square" />
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" />
</p>

---

## 🔬 Overview

This repository provides an **R pipeline** for:

1. Performing **differential expression (DE) analysis** of small RNAs (e.g., miRNAs) using **edgeR**.  
2. Retrieving **experimentally validated miRNA targets** using the [multiMiR](https://cran.r-project.org/web/packages/multiMiR/) package.  

It is designed for researchers working on **RNA-Seq / small RNA-Seq data** who want a streamlined workflow from raw counts → DE miRNAs → validated targets.

---

## ✨ Features

- Import raw read count data and experimental metadata.  
- Run **normalization, dispersion estimation, and DE analysis** with `edgeR`.  
- Extract **top differentially expressed miRNAs**.  
- Retrieve **validated miRNA–target interactions** from the multiMiR database.  
- Save results for downstream biological interpretation.  

---

## 📦 Installation

Make sure you have the following R packages installed:

```r
if (!requireNamespace("BiocManager", quietly = TRUE)) {
  install.packages("BiocManager")
}

# Bioconductor package
BiocManager::install("edgeR")

# CRAN package
install.packages("multiMiR")
````

---

## 📂 Input Files

The pipeline requires two inputs:

1. **Counts table** – (`counts_table.tsv`): raw read counts (miRNAs as rows, samples as columns).
2. **Sample metadata** – (`strains_factor.tsv`): experimental design/condition factor.

👉 Example datasets are bundled with the `multiMiR` package under `extdata/`.

---

## 🚀 Usage

Run the pipeline with:

```r
source("edgeR_multiMiR_pipeline.R")
```

This will:

1. Load the counts and metadata.
2. Perform **DE analysis** with edgeR.
3. Extract the **top 10 DE miRNAs**.
4. Query **multiMiR** for validated targets (default: mouse, `org = "mmu"`).

---

## 📊 Example Output

**Top 10 DE miRNAs (edgeR):**

```
[1] "mmu-miR-21a-5p" "mmu-miR-155-5p" "mmu-miR-34a-5p" ...
```

**multiMiR target results:**

```
   mature_mirna_id target_symbol   database
1   mmu-miR-21a-5p          PTEN  miRTarBase
2   mmu-miR-155-5p          SOCS1 TarBase
...
```

---

## ⚙️ Customization

* Change organism with `org = "hsa"` (for human), `org = "mmu"` (for mouse), etc.
* Adjust number of top DE miRNAs (e.g., `[1:20]` instead of `[1:10]`).
* Save results:

```r
write.csv(p_val_DE_edgeR$table, "DE_miRNAs_edgeR.csv")
write.csv(multimir_results@data, "multiMiR_targets.csv")
```

---

## 📖 References

* **edgeR**: Robinson MD, McCarthy DJ, Smyth GK (2010).
  *edgeR: a Bioconductor package for differential expression analysis of digital gene expression data.*
  *Bioinformatics, 26(1), 139–140.*

* **multiMiR**: Ru Y, Kechris KJ, Tabakoff B, et al. (2014).
  *The multiMiR R package and database: integration of microRNA–target interactions along with their disease and drug associations.*
  *Nucleic Acids Research, 42(17).*

---

