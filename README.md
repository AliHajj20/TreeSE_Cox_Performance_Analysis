# TreeSE_Cox_Performance_Analysis
The aim of this project is to implement Cox survival model on several data transformations stored in a single TreeSummarizedExperiment plus alternativeExperiment data structure, for the purpose of evaluating whether different transformations affect model performance and lead to different outputs.
1. Install Required Packages
To facilitate reproducibility, this project relies on a Docker image that includes many of the required dependencies. Instructions for installing and running the Docker image can be found here:
https://microbiome.github.io/OMA/docs/devel/pages/session_info.html#sec-docker-image

Additionally, users should install any remaining R packages listed at the beginning of the script if they are not already installed.

2. The data on which the analysis is performed can be found in this repository "biom.Rdata".
---
## Project Context

Master’s Program: Molecular Biology and Genetics
University: University of Pavia
Master’s Thesis Research Location: Turku Data Science Group, Turku, Finland
Supervisor: Leo Lahti
Degree Level: Master’s Thesis

---

## Data Description

- **Data Type:** Survival data from a microbiome study  
- **Source:** Public dataset  
- **Data File:** `biom.Rdata` (included in this repository)  
- **Data Structure:**  
  - Stored as a `TreeSummarizedExperiment` object  
  - Includes multiple transformed representations via `alternativeExperiment`

No additional data preprocessing is required beyond what is implemented in the analysis scripts.

---

## Methods

- **Statistical Model:** Cox Proportional Hazards Model  
- **Evaluation Metric:** Harrell's Concordance Index (C-index)  
- **Analysis Goal:**  
  To quantify and compare survival model performance across different statistical transformations of the microbiome abundance table while maintaining a consistent experimental design.

The analysis ensures that all transformations are evaluated under the same model and evaluation conditions.

---

## Software & Environment

- **Programming Language:** R  
- **IDE:** RStudio  

--
Results of the analysis:
![image](https://github.com/AliHajj20/TreeSE_Cox_Performance_Analysis/blob/8fe7e9f4fbc4511af4536b92316cd482ee72f9f6/model_performance.png)
This plot shows the C-index values for a Cox proportional hazards model when implemented on the abundance table of data transformations (Counts, CLR, Relative Abundance, and all pair log raio).
All the transformations are stored within a single TreeSummarizedExperiment data structure.
The All Pair Wise Log Ratio (APLR) has different dimensions compared to the other transformations; for that purpose, AlternativeExperiment was used to store the APLR statistical transformation format.
For more information regarding TreeSummarizedExperiment and AlternativeExperiment, check the following link:
https://microbiome.github.io/OMA/docs/devel/pages/containers.html
