# Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew
English yew is a long-lived tree widely distributed in Europe from sea level up to 2200m, often forming small stands and/or isolated populations. Several studies have shown phenotypic differences among populations of English yew across climatic gradients, while others have found signatures of ongoing selection and identified climate-related genes. These evidences suggest that local adaptation to climate may occur across the distribution range of the English yew. Moreover, recent declines and local extinctions of this species in many parts of Europe could exacerbate the effects of climate change, particularly for mountain populations where environmental disturbances are expected to be more severe. As a result, maladaptation - when fitness of individuals deviates from the optimal fitness in a given environment - could be of particular concern across the distribution range of the English yew.  This study aims to investigate the presence of local adaptation to climate across the species’ range and to forecast the potential maladaptation of the English yew to future climatic conditions.

# Scripts

## Formatting genomic and climatic data

Genomic and climatic data for the range-wide populations were formatting to perform genomic analyses of outlier detection and genomic offset. Additionnally, climatic and phenotypic data from an independent set of populations planted in a clonal bank were used to evaluate the genomic offset forecast. 

### [1. Genetic_filtering](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Genetic_filtering.html)

- Filtering genomic data for **population structure analyses** and **GEA and other analyses**
- Imputation of missing data for the second set of genomic data

### [2. Climatic data selection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Climatic_data.html)

- Extraction of climatic data from coordinates for the range-wide populations at 30 arc-seconds from Climate Downscaling tool (ClimateDT, Marchi et al. 2024).
- Visualization of the climatic variation across populations
- Selection of the reference period from which the populations are currently locally adapted (1901-1950)
- Identification of the main climatic drivers in our dataset by: pre-selection of climatic variables, most important variables to explain the genomic variation using OrdiR2step, remove over-collinear variables and calculate variance inflation factor (VIF).
- Calculatation of the future climatic data as the mean values from five global climate models (GCMs) under the socio-economic pathway 3-7.0 for the 2041-2060 period. 

### Phenotypic data clonal bank: soon

### Climatic data clonal bank: soon

## Insights into the potental local adaptation to climate

### [5. Variance partitioning](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Variance_partitioning.html)



### [6. Redundancy analyses (RDA) candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Redundancy_analyses_candidate_detection.html)

### [7. Latent factor mixed models (LFMM) candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/LFMM_candidate_detection.html)

### [8. BAYPASS candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/BAYPASS_candidate_detection.html)

### [9. Gradient forest (GF) candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Gradient_forest_candidate_detection.html)

### [10. Outlier selection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Outlier_selection.html)


## Genomic offset predictions

Soon


