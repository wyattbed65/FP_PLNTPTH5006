**General Description of This Project**

The data used from this project comes from the public database NCBI SRA. [Dataset](https://www.ncbi.nlm.nih.gov/sra/?term=SRR17703590)

Run Accession: SRR17703590	

Experiment Accession: SRX13866644

BioProject Accession: PRJNA799360 

I will be working with raw reads from a RNA-seq data set. This RNA data set was dervied from a tomato infected with Meloidogyne incognita, commonly known as root-knot nematode. For my project in graduate school, I will be working with Meloidogyne incognita and I wanted to have practice working with this data. This data is paired end Illumina NextSeq 500 RNA-seq reads. There are 4.3 gigabases, and the size of the file is 1.4 Gb. This data was published on 2023-02-01. 

The output of the data will be a Go-Term Enrichment analysis, which is used to determine biological functions of a set of genes. Before the Go-Term Enrichment analysis, the raw reads will have to be trimmed and placed into count tables. While in the count tables, as the RNA-sequnecing data is a comparison between the infected and control tomato roots, a differential expression analysis can be performed to look at differences of RNA expression. After the differential expression is performed, the genes that show differing RNA expression levels will be put into a GO-Term Enrichment analysis in order to understand the biological function of the differing genes active in root-knot nematode infection. This is from a public database and I have access to the data.

**Work Flow Steps**

1.) Transfer the public data in OSC

2.) I will first use TrimGalore to trim down the FASTQ data

3.) I will download a Solanum lycopersicum reference data set in order to run the Star alignment. Although the control group is included, I still need the reference dataset in order to properly align the control and experimental data sets.
[Reference Genome](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_036512215.1/)

4.) I will run a Star Alignment, and then use MultiQC to create an HTML report of the aligned data.

5.) I will run Salmon in order to convert this aligned data into count tables.

6.) I will use the count tables to perform a differenital expression analysis using a downloaded package (DEseq2).

7.) I will then sort the genes from the differential expression analysis into those that are upregulated and downregulated, filtering out genes with no change.  

8.) Using downloaded packages (such as clusterProfiler) I will use the sorted table and perform a Gene Enrichment Analysis to determine biological function of these genes.

All of these scripts will be performed using shell scripts in the form of a Slurm batch job. 
I will organize a distinct directory for each step, and the results will go into the specific directory related to the step. I do not plan to run a nf core-pipeline for this project. 

**Uncertain Aspects of My Project**

I am unsure how to perform the differential analysis and Go-Term analysis. I looked up both downloaded packages, but I am not completely sure how to get these packages or if they even work as expected. I am also unsure how to filter the data into only upregulated and downregulated genes. I will be able to get to the count tables using the information provided during the class. I will also be able to trim the data using TrimGalore. Regarding the rubric, I will use Slurm batch jobs, make sure my code is of quality, and will take copius notes to make sure my code is well documented and reproducible. 

**Why I Chose This Project**

For my graduate school project, I will be performing the same analysis as this project, but it will be with data that I have collected regarding developemnt of both root-knot nematode galls and maize transfer cells. I need to know how to do the exact analysis from this project in order to complete my project successfully. This will be amazing practice and a great reference for when I need to analyze my experimental data. 

