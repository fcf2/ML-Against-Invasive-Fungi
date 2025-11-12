# 🧫 ML-Against-Invasive-Fungi  
**Multi-target Drug Repurposing Against Invasive Fungi Using a Multi-strategy Approach in a Data-poor Setting**

This repository accompanies the research project **“Multi-target Drug Repurposing Against Invasive Fungi Using a Multi-strategy Approach in a Data-poor Setting.”**  
It provides a reproducible workflow for generating AI-based predictions of protein-ligand interactions across multiple fungal targets.

---

## 🧩 Reproducing the Research

Follow the steps below to reproduce the experiments and results.

### 1. Background Reading
Read the foundational work on AI-Bind:  
> **Improving the generalizability of protein-ligand binding predictions with AI-Bind**  
> DOI: [10.1038/s41467-023-37572-z](https://doi.org/10.1038/s41467-023-37572-z)

---

### 2. Set Up AI-Bind
Follow the official instructions at:  
👉 [https://github.com/ChatterjeeAyan/AI-Bind](https://github.com/ChatterjeeAyan/AI-Bind)

---

### 3. Data Sources
Download the following datasets from the **Broad Institute Drug Repurposing Hub**:

| File | Version | Source |
|------|----------|--------|
| `repurposing_samples_20200324.txt` | 2020-03-24 | [broadinstitute.org/repurposing](http://www.broadinstitute.org/repurposing) | 
| `repurposing_drugs_20180907.txt` | 2018-09-07 | [broadinstitute.org/repurposing](http://www.broadinstitute.org/repurposing) | 

---

### 4. Prepare Fungal Target Sequences
Extract the **target amino acid codes** (`target_aa_code`) for each fungal species from their respective `.pdb` structures:

- *Candida albicans* (**Ca**)  
- *Aspergillus fumigatus* (**Af**)  
- *Cryptococcus neoformans* (**Cn**)  
- *Paracoccidioides lutzii* (**Pl**)  
- *Fonsecaea pedrosoi* (**Fp**)

---

### 5. Generate Input Files
For each species above, create files containing:

| Field | Description |
|--------|-------------|
| **InChiKey** | Drug identifier |
| **SMILES** | Molecular structure in SMILES format |
| **target_aa_code** | Target protein amino acid sequence code |

Name the resulting files as follows:

Seq_Af_Uniprot
Seq_Ca_Uniprot
Seq_Cn_Uniprot
Seq_Pl_Uniprot
Seq_Fp_Uniprot

---

### 6. Run AI-Bind Predictions
Run **AI-Bind** to generate averaged predictions for each sequence file.

Expected output files:

Results_Teste_Ca_UP
Results_Teste_Cn_UP
Results_Teste_Pl_UP
Results_Teste_Af_UP
Results_Teste_Fp_UP

Each result file contains model-predicted protein-ligand binding scores for the respective fungal targets.

---

## 🧠 Citation

If you use this workflow, please cite:

>  
> *Multi-target Drug Repurposing Against Invasive Fungi Using a Multi-strategy Approach in a Data-poor Setting* 

---

## ⚙️ License
This project is shared for academic and research purposes.  
Please review the licensing terms of AI-Bind and the Broad Institute datasets before redistribution.

---


