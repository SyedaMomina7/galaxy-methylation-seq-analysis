# 🧬 DNA Methylation Analysis using Galaxy

## 📌 Project Summary

This repository presents a complete **DNA methylation sequencing (Methyl-Seq) analysis pipeline** implemented using the Galaxy platform. The workflow follows the Galaxy Training Network tutorial and demonstrates how bisulfite sequencing data can be processed to identify genome-wide methylation patterns and epigenetic regulation.

DNA methylation is a key epigenetic mechanism that influences gene expression without altering the underlying DNA sequence. This project showcases how computational tools can be used to analyze methylation profiles and detect biologically meaningful patterns.

---

##  Objectives

- Perform quality control on raw sequencing data  
- Align bisulfite-treated reads to a reference genome  
- Extract and quantify methylation levels  
- Visualize methylation patterns across genomic regions  
- Identify differentially methylated regions (DMRs)  

---

##  Methodology Overview

The analysis pipeline consists of the following major steps:

### 1.  Data Upload
Raw sequencing datasets were imported into the Galaxy environment for processing.

---

### 2.  Quality Control (Falco)

Quality assessment was performed using **Falco**, a high-performance alternative to FastQC.

The following metrics were evaluated:
- Per-base sequence quality  
- GC content distribution  
- Sequence duplication levels  
- Adapter contamination  

####  QC Results

##### Sample 1



<img width="738" height="335" src="https://github.com/user-attachments/assets/3188ca7e-5ff6-4926-bc42-31c25c444005" />

---

<img width="546" height="328" src="https://github.com/user-attachments/assets/06af4ad7-24a7-4332-8820-97e01c3b732c" />

---

<img width="728" height="325" src="https://github.com/user-attachments/assets/c18d930c-0dba-4f0e-ad97-59bdbecfc2df" />

---

##### Sample 2



<img width="586" height="326" src="https://github.com/user-attachments/assets/01085b7e-547d-4400-9abd-b728ae2f894f" />

---

<img width="735" height="339" src="https://github.com/user-attachments/assets/8feee5e4-48f2-4004-a730-f94c25cb8989" />

---

<img width="728" height="329" src="https://github.com/user-attachments/assets/e5b53df9-d6e2-429f-848d-898125c8cb2e" />



These results confirm that the sequencing data is of sufficient quality for downstream analysis.

---

### 3.  Alignment of Bisulfite Reads (bwameth)

Sequencing reads were aligned to the reference genome using **bwameth**, a bisulfite-aware aligner.

####  Key Considerations:
- Bisulfite treatment converts unmethylated cytosines to uracil (read as thymine)
- Specialized alignment is required to correctly interpret C→T conversions  
- bwameth efficiently handles these transformations and produces accurate mappings  

---

### 4.  Methylation Extraction and Analysis

Methylation levels were extracted from aligned reads and quantified across genomic regions. This step enables identification of methylated cytosines and overall methylation patterns.

---

### 5.  Genome-wide Visualization

Methylation signal tracks were generated and visualized using BigWig format.

<img width="660" height="660" src="https://github.com/user-attachments/assets/708fbb52-fe9a-4c52-9ba0-6807f3d967e3" />

This visualization represents methylation intensity across genomic coordinates, allowing identification of highly methylated regions.

---

### 6.  CpG Island Methylation Analysis

CpG islands are genomic regions with a high frequency of CpG sites and are often associated with gene regulatory elements.

<img width="866" height="551" src="https://github.com/user-attachments/assets/51944914-f9aa-4e5c-b97f-a7fe448bbcd2" />

The above heatmap illustrates methylation patterns across CpG regions, highlighting areas of enrichment and depletion.

---

### 7.  Differential Methylation Analysis

Differentially methylated regions (DMRs) were identified using statistical analysis tools.

**Output:**
- `metilene_qval_0.05.bedgraph`

These regions may correspond to biologically significant regulatory changes between conditions.

---

## 📁 Repository Structure


.
├── README.md
├── data/
├── results/
│ ├── bedwig.jpeg
│ ├── CpG_methylation.jpeg
│ ├── falco_qc_1.png
│ ├── falco_qc_2.png
├── workflows/


---

## 📂 File Descriptions

| File Type | Description |
|----------|------------|
| Falco Reports | Quality control summaries |
| RawData.txt | Sequencing statistics |
| `.bai` | Alignment index file |
| `.bw` (BigWig) | Genome-wide signal tracks |
| `.bed` | CpG island annotations |
| computeMatrix | Data for heatmap visualization |
| `.bedgraph` | Differential methylation results |
| Images | Visualization outputs |

---

##  Key Insights

- DNA methylation plays a crucial role in transcriptional regulation  
- Bisulfite sequencing requires specialized computational handling  
- CpG islands are primary targets for methylation studies  
- Differential methylation analysis can reveal epigenetic changes linked to biological conditions  

---

##  Reproducibility Workflow

To reproduce this analysis:

1. Upload raw sequencing data to Galaxy  
2. Perform quality control using Falco  
3. Align reads using bwameth  
4. Extract methylation information  
5. Convert outputs to BigWig format  
6. Generate visualization matrices (computeMatrix)  
7. Perform differential methylation analysis (Metilene)  

---

##  Reference

Galaxy Training Network  
https://training.galaxyproject.org/training-material/topics/epigenetics/tutorials/methylation-seq/tutorial.html  

---

## 📜 License

This project is based on Galaxy Training materials and is distributed under the **CC-BY 4.0 License**.

---

## ✨ Author

**Syeda Momina Assad**

---

## 📌 Acknowledgements

- Galaxy Project  
- Galaxy Training Network  
- Open-source bioinformatics community  
