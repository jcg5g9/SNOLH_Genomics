# Reproduce analyses for the Interior Highlands Hybridization project
<font size="+1">Follow the steps listed below in the <b><i>Analyses</i></b> section to reproduce analyses for this study. Each step below gives a summary of the analysis and directs you to a general code file (e.g., snolh_structure_analysis.Rmd below in Analysis 1) which then works through the analysis step-by-step. This general file will usually point you to other Rmd code, bash shell scripts, or python scripts.</font>

# Project: Interior Highlands Hybridization: Spotted, Smallmouth, Neosho, Ouachita, and Little River Bass (SNOLH)
Investigating hybridization and population structure among and within the Spotted Bass (<i>Micropterus punctulatus</i>), Smallmouth Bass (<i>M. dolomieu</i>), the newly elevated Neosho Bass (<i>M. velox</i>), and two other potentially distinct species in the Ouachita River Basin (the Ouachita and Little River Basses)

## Analyses

### Analysis 1: Population Structure and Hybrid Assignment
Summary: In this analysis, we assess hierarchical population genomic structure among and within Interior Highland species using the diagnostic SNP panel published by Long et al. (2021). We begin with a holistic analysis of population structure among Spotted Bass and all other Interior Highland species (Smallmouth Bass, Neosho Bass, Ouachita Bass, and Little River Bass) and diagnose hybrids between these species using SNPs diagnostic for Spotted Bass. We then exclude detected hybrids and continue with an analysis of population structure and hybridization among Smallmouth Bass, Neosho Bass, Ouachita Bass and Little River Bass. We again exclude any detected hybrids and move on to a final analysis of all Interior Highland species, excluding Spotted Bass and Smallmouth Bass.

#### Follow the Code: `snolh_structure_analysis.Rmd`
