# 🧫 ML-Against-Invasive-Fungi  
JCIM submitted paper: **Multi-target Drug Repurposing Against Invasive Fungi Using a Multi-strategy Approach in a Data-poor Setting**

This repository accompanies the research project/research paper **“Multi-target Drug Repurposing Against Invasive Fungi Using a Multi-strategy Approach in a Data-poor Setting.”**  
It provides a reproducible workflow for generating AI-based predictions of protein-ligand interactions across multiple fungal targets.

---

## 🧩 Reproducing the Research

Follow the steps below to reproduce the experiments and results.

### 1. Background Reading
Read the foundational work named AI-Bind:  
> **Improving the generalizability of protein-ligand binding predictions with AI-Bind**  
> DOI: [10.1038/s41467-023-37572-z](https://doi.org/10.1038/s41467-023-37572-z)

---

### 2. Set Up AI-Bind
Follow the official instructions at:  
👉 [https://github.com/ChatterjeeAyan/AI-Bind](https://github.com/ChatterjeeAyan/AI-Bind)

---

### 3. Data Sources
Download the following datasets from the **Broad Institute Drug Repurposing Hub** or from this github page:

| File | Version | Source |
|------|----------|--------|
| `repurposing_samples_20200324.txt` | 2020-03-24 | [broadinstitute.org/repurposing](http://www.broadinstitute.org/repurposing) | 
| `repurposing_drugs_20180907.txt` | 2018-09-07 | [broadinstitute.org/repurposing](http://www.broadinstitute.org/repurposing) | 

---

### 4. Prepare Fungal Target Sequences
Extract the **target amino acid codes/sequence** (`target_aa_code`) for each fungal species from their respective `.pdb` structures (download it from this github page):

- *Candida albicans* (**Ca**):  Ca_FAD.pdb
- *Aspergillus fumigatus* (**Af**):  Af_FAD.pdb
- *Cryptococcus neoformans* (**Cn**):  Cn_FAD.pdb
- *Paracoccidioides lutzii* (**Pl**):  Pl_FAD.pdb
- *Fonsecaea pedrosoi* (**Fp**): Fp_FAD.pdb

---

### 5. Generate Input Files
For each species above, download the input files from this github page:

| Field | Description |
|--------|-------------|
| **InChiKey** | Drug identifier |
| **SMILES** | Molecular structure in SMILES format |
| **target_aa_code** | Target protein amino acid sequence code |

Name the files as follows:

1 Exp3(targets from uniprot)-Seq Af Uniprot.csv  
2 Exp3(targets from uniprot)-Seq Ca Uniprot.csv  
3 Exp3(targets from uniprot)-Seq Cn Uniprot.csv  
4 Exp3(targets from uniprot)-Seq Pl Uniprot.csv  
5 Exp3(targets from uniprot)-Seq Fp Uniprot.csv  

---

### 6. Run AI-Bind Predictions
Run **AI-Bind** to generate averaged predictions for each sequence file.

Expected output files:

Results_Teste_Ca_UP  
Results_Teste_Cn_UP  
Results_Teste_Pl_UP  
Results_Teste_Af_UP  
Results_Teste_Fp_UP  

### 7. Filtering  

Each result file contains model-predicted protein-ligand binding scores for the respective fungal targets. Download it from this github page or use the ones you have generated.  Among all compounds from DRH predicted as interacting with all five fungi targets, rank them according to the maximal prediction score over the five targets. Exclude those duplicated, already reported to have antifungal activity, and the similar compounds (like Bacitracin and Bacitracin-zinc or Colistin and Colistimethate).


### 8. Molecular Docking  

With GOLD software Version 2021.3.0, perform the molecular docking using the TRR1 from P. lutzii and all the selected ligands. Select the top 10 compounds showing the highest number of interactions within the known TRR1 catalytic site.

### 9. Characterizing the binding interactions   

Set up the PDBePISA:

https://www.ebi.ac.uk/pdbe/pisa/

Calculate the number of hydrogen bonds and salt bridges in the known catalytic site and positioning between the ligand and the target. Select the molecules with the highest number of hydrogen bonds and salt bridges. The results are: Bleomycetin, Oritavancin, and LY2510924.

### 10. MIC Experiments & Enzymatic Assay

The compounds Bleomycetin, Oritavancin, LY2510924 (methodology described in Figure 1) and Nisin, Daptomycin, Bacitracin, Colistin sulfate, Polymyxin B Sulfate and Linaclotide (selected from Table 1 AI-Bind ranking) underwent MIC experiments on the three fungal species available in the laboratory (C. albicans, A. fumigatus, P. brasiliensis). They were tested by broth microdilution assay to determine the MIC in vitro (Table 3). Calculate Km and Vmax values of Bleomycetin compared to the control and its affinity with the catalytic site of TRR1.


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


