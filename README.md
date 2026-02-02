# single-cell-islet-pipeline-seurat

## 🧬 Project Overview
This project reproduces and extends key analyses (Figure 1 and Figure 2) from a published Nature paper using publicly available single-cell RNA-seq data from human pancreatic islets.

Rather than focusing only on final figures, I rebuilt the **entire scRNA-seq pipeline from raw FASTQ files to biological interpretation**, with an emphasis on understanding methodological choices, reproducibility, and downstream analysis decisions.

---

## 🎯 Objectives
- Reproduce core clustering and cell-type structure reported in the original study
- Implement a complete end-to-end scRNA-seq pipeline
- Compare Seurat-based analysis with the original Conos + PAGODA workflow
- Understand how different computational tools affect visualization but preserve biological meaning

---

## 🛠️ Pipeline Summary

### 1. Preprocessing
- Adapter trimming and quality filtering using **fastp**
- Quality assessment using **FastQC / MultiQC**

### 2. Alignment
- Reads aligned to **hg38** using **STAR (2-pass alignment)**
- Uniquely mapped reads retained

### 3. Quantification
- Gene-level count matrices generated from STAR-aligned BAM files
- Input formatted for downstream Seurat analysis

### 4. Quality Control (Post-alignment)
Cells were filtered based on:
- mRNA read counts
- Percent uniquely mapped reads
- Percent exonic reads
- Mitochondrial read percentage

Filtering thresholds were aligned as closely as possible with those described in the original paper.

### 5. Normalization & Dimensionality Reduction
- Log-normalization (Seurat)
- Highly variable gene selection
- PCA for dimensionality reduction
- UMAP for visualization

### 6. Clustering & Annotation
- Graph-based clustering
- Cell-type annotation using known pancreatic marker genes

### 7. Downstream Analysis
- Differential expression analysis
- Gene co-expression network analysis using **dGCNA**
- Functional interpretation of cell-type-specific networks

---

## 📊 Key Results
- Cluster structure and major pancreatic cell types match the original study
- Visual differences observed due to different normalization and integration strategies
- Biological interpretations remain consistent across pipelines

---

## 🔍 Tools & Technologies
- R, Seurat
- STAR
- fastp, FastQC, MultiQC
- ggplot2
- dGCNA

---

## 📁 Repository Structure# single-cell-islet-pipeline-seurat
