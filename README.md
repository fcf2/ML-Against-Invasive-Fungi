# ML-Against-Invasive-Fungi
Multi-target Drug Repurposing Against Invasive Fungi Using a Multi-strategy Approach in a Data-poor Setting
To reproduce this research:
1- Read: Improving the generalizability of protein-ligand binding predictions with AI-Bind (https://doi.org/10.1038/s41467-023-37572-z)
2- Follow the instructions at: https://github.com/ChatterjeeAyan/AI-Bind
3- Extract from http://www.broadinstitute.org/repurposing the file: sample information, version 3/24/2020
4- Extract from http://www.broadinstitute.org/repurposing the file: drug information, version 9/7/2018
5- Extract the target_aa_code for each of the fungi Ca, Af, Cn, Pl, Fp from the .pdb files
6- Generate the files containing InChiKey,	SMILE,	target_aa_code for each of the fungi Ca, Af, Cn, Pl, Fp (Seq Af Uniprot, Seq Ca Uniprot, Seq Cn Uniprot, Seq Pl Uniprot and Seq Fp Uniprot)
7- Generate the AI-Bind Averaged Predictions for each of the Seq Af Uniprot, Seq Ca Uniprot, Seq Cn Uniprot, Seq Pl Uniprot and Seq Fp Uniprot. The outcomes are: Results_Teste_Ca_UP, Results_Teste_Cn_UP, Results_Teste_Pl_UP, Results_Teste_Af_UP, Results_Teste_Fp_UP.
