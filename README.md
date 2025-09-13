# 🧬 miRNA-DE-multiMiR

<p align="center">
  <img src="https://img.shields.io/badge/R-4.3%2B-blue?style=flat-square&logo=r" />
  <img src="https://img.shields.io/badge/edgeR-DE%20Analysis-green?style=flat-square" />
  <img src="https://img.shields.io/badge/multiMiR-miRNA%20Targets-purple?style=flat-square" />
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" />
</p>  

---

## 🔬 Overview

This R pipeline performs **differential expression (DE) analysis** of miRNAs using **edgeR** and retrieves **validated miRNA targets** using **multiMiR**. Ideal for RNA-Seq/small RNA-Seq studies.

---

## 🚀 Features

* Load raw counts and sample metadata.
* Normalize data and perform DE analysis with edgeR.
* Extract top DE miRNAs.
* Query multiMiR for validated miRNA-target interactions.
* Save results for downstream analysis.

---

## 📦 Installation

```r
install.packages("BiocManager")
BiocManager::install("edgeR")
install.packages("multiMiR")
```

---

## 📂 Usage

```r
source("edgeR_multiMiR_pipeline.R")
```

* Performs DE analysis.
* Retrieves top DE miRNAs and validated targets.
* Supports human (`org="hsa"`) or mouse (`org="mmu"`).

---

## 📖 References

* **edgeR**: Robinson MD et al., Bioinformatics, 2010.
* **multiMiR**: Ru Y et al., Nucleic Acids Res, 2014.

---

If you want, I can also make an **ultra-short one-paragraph version** suitable for GitHub home page display. Do you want me to do that?
