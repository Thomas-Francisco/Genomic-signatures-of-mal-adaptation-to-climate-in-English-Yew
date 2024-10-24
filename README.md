# Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew
English yew is a long-lived tree widely distributed in Europe from sea level up to 2200m, often forming small stands and/or isolated populations. Several studies have shown phenotypic differences among populations of English yew across climatic gradients, while others have found signatures of ongoing selection and identified climate-related genes. These evidences suggest that local adaptation to climate may occur across the distribution range of the English yew. Moreover, recent declines and local extinctions of this species in many parts of Europe could exacerbate the effects of climate change, particularly for mountain populations where environmental disturbances are expected to be more severe. As a result, maladaptation - when fitness of individuals deviates from the optimal fitness in a given environment - could be of particular concern across the distribution range of the English yew.  This study aims to investigate the presence of local adaptation to climate across the species’ range and to predict the potential maladaptation of the English yew to future climatic conditions.

# Scripts

All the scripts associated with the HTML presented below are available in the folder [Scripts](https://github.com/Thomas-Francisco/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/tree/main/Scripts)

## Formatting genomic and climatic data

Genomic and climatic data for the range-wide populations were formatted to perform population structure analyses and genomic analyses for outlier detection and genomic offset. Additionally, climatic and phenotypic data from an independent set of populations planted in a clonal bank were used to evaluate the genomic offset forecast."

### [1. Genetic_filtering](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Genetic_filtering.html)

- Filtering genomic data for **population structure analyses** and **GEA and other analyses**
- Imputation of missing data for the second set of genomic data

### [2. Climatic data selection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Climatic_data.html)

- Extraction of climatic data from coordinates for the range-wide populations at 30 arc-seconds using the Climate Downscaling tool (ClimateDT, Marchi et al. 2024).
- Visualization of the climatic variation across populations
- Selection of the reference period from which the populations are currently locally adapted (1901-1950)
- Identification of the main climatic drivers in our dataset by : pre-selecting the climatic variables, identifying the most important variables to explain the genomic variation using OrdiR2step, removing over-collinear variables and calculating the variance inflation factor (VIF).
- Calculation of the future climatic data as the mean values from five global climate models (GCMs) under the socio-economic pathway 3-7.0 for the 2041-2060 period.

### [2. Population structure](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Population_structure.html)

- Principal component analyses at the individual and population levels
- STRUCTURE clustering analysis
- Graphical representation 

### Phenotypic data clonal bank

soon

### Climatic data clonal bank

soon


## Insights into the potental local adaptation to climate

Local adaptation to climate have been investigated by first searching for isolation by environment and then by identifying candidate loci associated with climatic predictors.

### [6. Variance partitioning](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Variance_partitioning.html)

- RDA and pRDA were used to disentangle the influence of demographic history, geography and climate on the genomic variation across populations, and to search for potential isolation by environment (IBE) between populations, following the procedure of Capblancq & Forester (2021)
- Several proxies were used for geography and demographic history

### [7. Redundancy analyses (RDA) candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Redundancy_analyses_candidate_detection.html)

- Identification of candidate loci using the linear RDA method not correcting for population structure
- Identification of candidate loci using the pRDA method correcting for population structure using PC axes.
- Dectection of outliers using the Mahalanobis distance method
- Two sets of thresholds: FDR 10% and FDR 5%
- Calculation of p-values for each locus for the RDA method, this will be used in the *outlier selection script*
- Graphical visualization

### [8. Latent factor mixed models (LFMM) candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/LFMM_candidate_detection.html)

- Identification of candidate loci using the multivariate approach developped in LFMM2 (Gain et al. 2020)
- Latent factors were used to account for population structure, we determinated the number of latent factor required
- Two sets of thresholds: FDR 10% and FDR 5%
- Graphical visualization

### [9. BAYPASS candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/BAYPASS_candidate_detection.html)

- Method developped by Mathieu Gautier (2015)
- Core model used to construct the Omega matrix to account for population structure
- Standard covariate model (STD) used to calculate the association between SNPs and climatic predictors
- Five independent runs
- Two sets of thresholds: Bayes factor (BF) of 8 and 10
- Graphical visualization

### [10. Gradient forest (GF) candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Gradient_forest_candidate_detection.html)

- Non- linear machine learning algorithm used as a GEA method by Fitzpatrick et al. (2021)
- GF-raw not accounting for population structure
- GF-corrected accounting for population structure using the LFMM-corrected matrix
- Five independent runs
- Two sets of thresholds: top 5% and 1% of the overlapping SNPs across runs with the highest association with climatic predictors

### [11. Outlier selection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Outlier_selection.html)

- Identification of overlapping candidates across at least two GEA methods
- Candidates in linkage disequilibrium (LD) within the same contig were removed to retain only one.
- Random set of SNPs was built
- Random set of SNPs with the same allelic frequencies as the outliers was also built
  
## Genomic offset predictions

Soon

## Evaluation of the GEA models and the genomic offset predictions

soon

# Sources

