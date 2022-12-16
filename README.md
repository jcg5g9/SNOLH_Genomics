# Reproduce analyses for the Interior Highlands Hybridization project [PUBLICATION CITATION]
<font size="+1">Follow the steps listed below in the <b><i>Analyses</i></b> section to reproduce analyses for this study. Each step below gives a summary of the analysis and directs you to a general code file (e.g., snolh_structure_analysis.Rmd below in Analysis 1) which then works through the analysis step-by-step. This general file will usually point you to other Rmd code, bash shell scripts, or python scripts.</font>

# Project: Interior Highlands Hybridization: Spotted, Smallmouth, Neosho, Ouachita, and Little River Bass (SNOLH)
Investigating hybridization and population structure among and within the Spotted Bass (SPB; <i>Micropterus punctulatus</i>), Smallmouth Bass (SMB; <i>M. dolomieu</i>), the newly elevated Neosho Bass (NB; <i>M. velox</i>), and two other potentially distinct species in the Ouachita River Basin, the Ouachita Bass (OB; <i>M. cf. dolomieu</i> Ouachita River) and the Little River Bass (LRB; <i>M. cf. dolomieu</i> Little River)

## General information on repository structure
This is a publicly visible GitHub repository storing code (and a small amount of data, although we have done our best to avoid uploading large amounts of data due to the limited storage) for [PUBLICATION CITATION]. In the home directory of the repository (SNOLH_Genomics), you will find a README.md file (the source script for this information), the R Project file (SNOLH_Genomics.Rproj), a project info file (project_info, which includes all important information on data/sequence procurement for this project along with a full data summary produced by Floragenex, Inc.), and [number of analyses] different "analysis" directories, each of which corresponds with a specific analysis conducted in our study:

1) filtering_analysis
2) structure_analysis
3) introgress_analysis

Within each analysis directory, you will find an R markdown script (.Rmd) with the name of the analysis, which contains all of the code needed to run the full analysis. Additionally, you will find:

1) code

The code directory will store all source code, shell scripts, lists of bash commands, and software packages needed for analysis. 

Once you have downloaded the repository and located the code directory, you should create two additional sub-directories within each analysis (on the same level as the code directory):

2) data
3) figures

The data directory will store all processed data and metadata needed for analysis. The figures folder will contain any raw figures generated in ggplot for each analysis. Ideally, the Rmd script should have paths set up so that the code reads all data and scripts and generates figures seamlessly.

## Using the code
To reproduce all analyses in [PUBLICATION CITATION], download this data repository and place in a desired home directory. This may be done on your local machine, but we recommend downloading to a high-performance computing cluster so that all code will run seamlessly in one environment, as long as Rstudio is installed and the GUI can be called on the cluster.

Once all directories are downloaded, create a new sub-directory within the home directory (same level as the seven analysis directories, .Rproj, README.md, etc.) called `/raw_data`. This is where you will store the raw genomic data and associated sample metadata (see <i><b>Data</i></b> section below).

## Data
Raw genotype data and accompanying metadata are available at Zenodo.org: [LINK]

Download these data into to your `/raw_data` directory within the home working directory.

You should have 2 new items in the directory: <br>

1. snolh_genotype_data.xlsx <br>
2. snolh_metadata.xlsx <br>

If you have any questions or issues with data and/or code, please don't hesitate to contact me: jcgunn@uvm.edu

## Analyses

### Analysis 1: Filtering Analysis
In this analysis, we clean and filter the full genotype data for 487 black bass individuals, which was derived from the diagnostic SNP panel developed by Long et al. (2021) and prepare the data for analysis in Structure and NewHybrids (See Analysis 2). Specifically, we filter the dataset based on three criteria: 1) out poor quality SNP loci (loci that failed to genotype in over 20% of samples); 2) poor quality samples (samples that failed to genotype in over 20% of loci); and 3) potential duplicate samples (samples that are greater than 95% identical across loci).

#### Follow the Code: `snolh_filtering_analysis.Rmd`

### Analysis 2: Population Structure and Hybrid Assignment
In this analysis, we assess hierarchical population genomic structure among and within Interior Highland species using the diagnostic SNP panel published by Long et al. (2021). We begin with a holistic analysis of population structure among Spotted Bass and all other Interior Highland species (Smallmouth Bass, Neosho Bass, Ouachita Bass, and Little River Bass) and diagnose hybrids between these species using SNPs diagnostic for Spotted Bass. We then exclude detected hybrids and continue with an analysis of population structure and hybridization among Smallmouth Bass, Neosho Bass, Ouachita Bass and Little River Bass. We again exclude any detected hybrids and move on to a final analysis of all Interior Highland species, excluding Spotted Bass and Smallmouth Bass.

#### Follow the Code: `snolh_structure_analysis.Rmd`

### Analysis 3: Introgression Analysis
In this analysis, we further investigate hybridization and introgression within populations that were inferred to contain hybrids based on NEWHYBRIDS analysis (Analysis 2). We use the R package Introgress to regress interspecific heterozygosity on hybrid index for inferred F1, F2, and backcross individuals at each hierarchical level of hybrid analysis conducted in Analysis 2. With this analysis, we determine whether hybrids are of very recent origin (first or second generation) or if they show a genetic signature of deeper time hybridization. We also infer from this analysis the extent to which non-native alleles have introgressed into the native distribution of each Smallmouth Bass species complex (SMBC) species.

#### Follow the Code: `snolh_introgress_analysis.Rmd`
