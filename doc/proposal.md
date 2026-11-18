**General Description of This Project**

The data used from this project comes from the public database NCBI SRA. 

[Sample 1](https://www.ncbi.nlm.nih.gov/sra/?term=SRR17703590)

[Sample 2](https://www.ncbi.nlm.nih.gov/sra/SRX13866638[accn])
	
Experiment Accession: PRJNA799360

Sample 1 Accession: SAMN25159909  

Sample 2 Accession: SAMN25159907 

I will be working with raw reads from a RNA-seq data set. This RNA data set was dervied from a tomato infected with Meloidogyne incognita, commonly known as root-knot nematode. Sample 1 consists of a tomato that has not been infected, or the control. Sample 2 represents RNA sequencing data of roots that have been infected. Both of these were taken 7 days after inoculation of the nematodes. For my project in graduate school, I will be working with Meloidogyne incognita and I wanted to have practice working with this data. This data is paired end Illumina NextSeq 500 RNA-seq reads. For sample 1 there are 4.3 gigabases, and the size of the file is 1.4 Gb. For sample 2, there are 5.6 gigabases, the size of the file is 1.9 Gb. This data was published on 2023-02-01.

The output of the data will be a Go-Term Enrichment analysis, which is used to determine biological functions of a set of genes. Before the Go-Term Enrichment analysis, the raw reads will have to be trimmed and placed into count tables. While in the count tables, as the RNA-sequnecing data is a comparison between the infected and control tomato roots, a differential expression analysis can be performed to look at differences of RNA expression. After the differential expression is performed, the genes that show differing RNA expression levels will be put into a GO-Term Enrichment analysis in order to understand the biological function of the differing genes active or repressed in root-knot nematode infection. This is from a public database and I have access to the data.

**Work Flow Steps**

1.) Transfer the public data in OSC for both the control and 7 days post infection roots.

2.) I will first use TrimGalore to trim down the FASTQ data

3.) A FASTQC report will be created to ensure that reads that are not of quality have been properly trimmed by TrimGalore.

4.) I will download a Solanum lycopersicum reference data set in order to run the Star alignment. Although the control group is included, I still need the reference dataset in order to properly align the control and experimental data sets.
[Reference Genome](https://www.ncbi.nlm.nih.gov/datasets/genome/GCF_036512215.1/)

5.) I will run a Star Alignment, and then use MultiQC to create an HTML report of the aligned data.

6.) I will run Salmon in order to convert this aligned data into count tables.

7.) I will use the count tables to perform a differenital expression analysis using a downloaded package (DEseq2).

8.) I will then sort the genes from the differential expression analysis into those that are upregulated and downregulated, filtering out genes with no change.  

9.) Using downloaded packages (such as clusterProfiler) I will use the sorted table and perform a Gene Enrichment Analysis to determine biological function of these genes.

All of these scripts will be performed using shell scripts in the form of a Slurm batch job. 
I will organize a distinct directory for each step, and the results will go into the specific directory related to the step. I do not plan to run a nf core-pipeline for this project. 

**Uncertain Aspects of My Project**

I am unsure how to perform the differential analysis and Go-Term analysis. I looked up both downloaded packages, but I am not completely sure how to get these packages or if they even work as expected. I am also unsure how to filter the data into only upregulated and downregulated genes. I will be able to get to the count tables using the information provided during the class. I will also be able to trim the data using TrimGalore. Regarding the rubric, I will use Slurm batch jobs, make sure my code is of quality, and will take copius notes to make sure my code is well documented and reproducible. 

**Why I Chose This Project**

For my graduate school project, I will be performing the same analysis as this project, but it will be with data that I have collected regarding developemnt of both root-knot nematode galls and maize transfer cells. I need to know how to do the exact analysis from this project in order to complete my project successfully. This will be amazing practice and a great reference for when I need to analyze my experimental data. 

