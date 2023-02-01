# Longitudinal scRNAseq of human pancreatic slices

Summary

This repository contains coding scripts utilized for the analysis performed in the "Single cell resolution analysis of the human pancreatic ductal progenitor cell niche" publication (Qadir/Alvarez-Cubela et. al, 2020). The purpose of providing the code here is to allow for transparency and robust data-analysis reproducibility. Most of the steps used for data analysis and visualization have been optimised for an average computing environment (for the year 2019). Some analyses however, require a high-performace computing environment (see computing environment). The methodology has already been described extensively in the manuscript. However, this analysis relies heavily on powerful scRNAseq analysis algorithms developed by the Satija lab, namely Seurat (Butler et al., 2018: Nature Biotechnology; Stuart et al., 2018: Cell) (for a complete list of dependencies and code utilized see analysis & visualization programs).

Overall design

HPSs from non-diabetic donors (n=3) were received from the Network for Pancreatic Organ Donors with Diabetes (nPOD). Slices were placed on AirHive perfluorocarbon-based culture dishes and optimized HPS medium for 24hr. After a 24h acclimation period, slices (6/group) were assigned to one of the following two groups: Control, where HPSs were cultured for 10 days; and BMP-7, in which HPSs received 100 ng/ml of BMP-7 in the medium for 5 days and remained in culture without BMP-7 for an additional 5 days. 3 slices were collected at day 5 (time point 1) for both groups; and the remaining ones at day 10 (time point 2). Harvested slices were dissociated into single cells and scRNAseq performed.

Downloading Data files

Data files utilized in this analysis have been deposited in the Gene Expression Omnibus (GEO), gene expression data repository at the NIH. Data are part of the GSE131886 high-thoroughput sequencing repository and can be found here. Data files have been renamed allowing for sample-origin information to be incorporated. Supplementary files contain Cellranger output files, which have been renamed to ensure clarity. Change file names (of filtered information) to 'matrix.mtx.gz', 'barcodes.tsv.gz' and 'features.tsv.gz' after seperating files into donor specific folders. This is necessary, to allow Seurat to read these files. Seruat cannot read files named in their current form. Please note, GSE raw data files are freely available for public download on GEO. If you would like further files such as seurat objects to download, please email the project leader for requests.

Data sub-structure

We povide raw FASTQ files generated from single-cell cDNA libraries sequenced by the Illumina sequencing platform, along with unfiltered post-alignment count files generated by the Cellranger v3.0.1 software. In addition we also provide a gene expression matrix containing data on filtered gene counts across our dataset.

FASTQ files

These are sequencing reads generated by the Illumina sequencing platform. Files contain raw reads and sequencing efficiency information. These are the input files for the Cellranger software.

Cellranger output (processed gene-counts of single cells/barcodes)

This contains data outputs of Cellranger v3.0.1, which was run using default settings. Code used to analyze data is a part of this repository. This data contains filtered/unfiltered count files for gene expression across barcodes/cells.

Data analysis of Longitudinal scRNAseq of human pancreatic slices datasets

Preliminary data-analyses involving n=3 de-identified human exocrine-pancreata derived ALK3+ cells are included in this file. This includes data thresholding, normalization, subsetting, linear dimensionality reduction (PCA), non-linear multimodal dimensionality reduction (PCA/UMAP), clustering, and data visualization.



Analysis and visualization programs
Cellranger software from 10X Genomics:
Cellranger
R and R's integrated developmental environment RStudio:
R 4.1.3 (2022-03-10) (x64 bit)
Rstudio v2022.7.1.554, release_name- "Spotted Wakerobin" (x64 bit)
RTools v3.3.X



Computing environment
Hardware and OS environment for running Cellranger
Environment 1
Processor: Intel Sandy Bridge E5-2670 (16cores x 16 threads)
RAM: 25GB
OS: CentOS 6.5
Environment 2
Hardware integrated into the Pegasus Supercomputing array at the University of Miami
Hardware and OS environment for running Seurat 
Analysis was performed/replicated on each of these computing systems, and ran optimally.

Processor	Intel(R) Xeon(R) Gold 6230R CPU @ 2.10GHz   2.10 GHz
Installed RAM	96.0 GB (94.6 GB usable)
System type	64-bit operating system, x64-based processor
Edition	Windows 10 Enterprise
OS build	19044.2486
Experience	Windows Feature Experience Pack 120.2212.4190.0

Hardware and OS environment for running RNA velcoty- scVelo and Velocyto
IBM Power9/Nvidia Volta – 6 Racks
IBM declustered storage – 2 Racks
96 IBM Power 9 servers
30TB RAM (256/node)
64 bit scalar
400 TB shared home
2 @ 1.99 TB ssd local storage
-----
IPython             8.4.0
jupyter_client      7.3.5
jupyter_core        4.11.1
-----
Python 3.9.12 | packaged by conda-forge | (main, Mar 24 2022, 23:25:27) [GCC 10.3.0]
Linux-4.14.0-115.el7a.ppc64le-ppc64le-with-glibc2.17
Contributors
Mayur Doke - University of Miami - to contact please Email
Mirza Muhammad Fahd Qadir - Github - to contact please Email
The JDB Lab - Github - Diabetes Research Institute, UM
Lead Contacts
Dr. Juan Dominguez-Bendala PhD. - Diabetes Research Institute, UM - to contact please Email
Dr. Ricardo Pastori PhD. - Diabetes Research Institute, UM - to contact please Email
Acknowledgements
Diabetes Research Institute Foundation (DRIF)
Grant ID	Grant title	Affiliation	Name
R01 DK130846	Single-cell longitudinal analysis of regeneration in human pancreatic slices	University of Miami School of Medicine	Juan Dominguez-Bendala
R01 DK130846	Single-cell longitudinal analysis of regeneration in human pancreatic slices	University of Miami School of Medicine	RICARDO L PASTORI
U01 DK120393	HIGH-RESOLUTION CHARACTERIZATION OF HUMAN DUCTAL PROGENITOR CELLS AND THEIR REGENERATION POTENTIAL	University of Miami School of Medicine	Juan Dominguez-Bendala
U01 DK120393	HIGH-RESOLUTION CHARACTERIZATION OF HUMAN DUCTAL PROGENITOR CELLS AND THEIR REGENERATION POTENTIAL	University of Miami School of Medicine	RICARDO L PASTORI
If this was useful to you please dont forget to cite, star and fork this repository
