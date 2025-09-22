# Genomic signatures of climate-driven (mal)adaptation in an iconic conifer, the English yew (Taxus baccata L.)
English yew is a long-lived tree widely distributed in Europe from sea level up to 2200m, often forming small stands and/or isolated populations. Several studies have shown phenotypic differences among populations of English yew across climatic gradients, while others have found signatures of ongoing selection and identified climate-related genes. These evidences suggest that local adaptation to climate may occur across the distribution range of the English yew. Moreover, recent declines and local extinctions of this species in many parts of Europe could exacerbate the effects of climate change, particularly for Mediterranean populations at the warm and arid range limit, and for those in other sensitive environments, such as high-elevation mountain regions, where climate-induced stress is already being observed and/or is predicted to be particularly strong in the near future (Mendoza et al. 2009; Knight 2022). The main objectives of this study are i) to investigate patterns of local adaptation to climate in T. baccata, ii) to evaluate the potential of genomic offset to predict population maladaptation under novel climatic conditions for a species with a highly-fragmented distribution, and iii) to gain insight into the potential vulnerability of T. baccata populations to future climate by linking information on the current degree of local adaptation, the historical capacity of gene flow and the predicted future climate maladaptation. To meet these objectives, we first used climatic and genomic data from 29 populations across the species’ European range to identify gene-climate relationships, as well as candidate climate-associated loci; second, we computed the distance between the observed and predicted genomic composition to identify populations deviating  from average gene-climate relationships (subsequently called  ‘genomic discrepancy index’); and third, we calculated historical effective migration and genetic differentiation between populations to determine potential trends in gene flow capacity in the near future, assuming conservatism of historical patterns. Finally, we calculated genomic offsets using two methods and evaluated their predictions using phenotypic traits related to growth, growth phenology, reproductive phenology and drought/temperature tolerance, measured in plants from 26 populations grown in a comparative experiment. 

# Scripts

All the scripts associated with the HTML presented below are available in the folder [Scripts](https://github.com/Thomas-Francisco/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/tree/main/Scripts)

## Formatting genomic and climatic data

Genomic and climatic data for the range-wide populations were formatted to perform population structure analyses and genomic analyses for outlier detection and genomic offset. Additionally, climatic and phenotypic data from an independent set of populations planted in a clonal bank were used to evaluate the genomic offset forecast.

### [1. Genetic_filtering](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Genetic_filtering.html)

- Filtering genomic data for **population structure analyses** and **GEA and other analyses**
- Imputation of missing data for the second set of genomic data

### [2. Climatic data selection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Climatic_data.html)

- Extraction of climatic data from coordinates for the range-wide populations at 30 arc-seconds using the Climate Downscaling tool (ClimateDT, Marchi et al. 2024).
- visualisation of the climatic variation across populations
- Selection of the reference period from which the populations are currently locally adapted (1901-1950)
- Identification of the main climatic drivers in our dataset by : pre-selecting the climatic variables, identifying the most important variables to explain the genomic variation using OrdiR2step, removing over-collinear variables and calculating the variance inflation factor (VIF).
- Calculation of the future climatic data as the mean values from five global climate models (GCMs) under the socio-economic pathway 3-7.0 for the 2041-2060 period.

### [3. Population structure](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Population_structure.html)

- Principal component analyses at the individual and population levels
- STRUCTURE clustering analysis
- Graphical representation 

### [4. Phenotypic data clonal bank](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Phenotypic_data_clonal_bank.html)

- Phenotypic data distribution and sampling years
- BLUPs models using GLMM MCMC models
- Evaluation of BLUPs models
- Population BLUPs estimate for each traits

### [5. Climatic data clonal bank](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Climatic_data_clonal_bank.html)

- Comparison of point-based layer and raster data
- Climatic data for the populations planted in the clonal bank for the reference period in their natural environment
- Climatic data in the clonal bank for each trait for the period: clonal bank establishment to the last year of measurement of the trait
- Comparison of the climate of the clonal bank and the climate of each population planted in the clonal bank


## Insights into the potental local adaptation to climate

Local adaptation to climate has been investigated by first establishing whether climate is a driver of genetic differentiation between populations, and then identifying candidate loci associated with climatic predictors.

### [6. Variance partitioning](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Variance_partitioning.html)

- RDA and pRDA were used to disentangle the influence of demographic history, geography and climate on the genomic variation across populations, and to search for potential climate-driven genetic differentiation between populations, following the procedure of Capblancq & Forester (2021)
- Several proxies were used for geography and demographic history

### [7. Redundancy analyses (RDA) candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Redundancy_analyses_candidate_detection.html)

- Identification of candidate loci using the linear RDA method not correcting for population structure
- Identification of candidate loci using the pRDA method correcting for population structure using PC axes.
- Dectection of outliers using the Mahalanobis distance method
- Two sets of thresholds: FDR 10% and FDR 5%
- Calculation of p-values for each locus for the RDA method, this will be used in the *outlier selection script*
- Graphical visualisation

### [8. Latent factor mixed models (LFMM) candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/LFMM_candidate_detection.html)

- Identification of candidate loci using the multivariate approach developped in LFMM2 (Gain et al. 2020)
- Latent factors were used to account for population structure, we determinated the number of latent factor required
- Two sets of thresholds: FDR 10% and FDR 5%
- Graphical visualisation

### [9. BAYPASS candidate detection](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/BAYPASS_candidate_detection.html)

- Method developped by Mathieu Gautier (2015)
- Core model used to construct the Omega matrix to account for population structure
- Standard covariate model (STD) used to calculate the association between SNPs and climatic predictors
- Five independent runs
- Two sets of thresholds: Bayes factor (BF) of 8 and 10
- Graphical visualisation

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
- All outlier set was built
  
## Genomic offset predictions

### [12. RDA genomic offset and GDI index](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/RDA_Genomic_offset.html)

- RDA GEA models
- Comparison loading and predicted RDA approaches 
- Genomic discrepancy index (GDI) calculation for the RDA reference period model
- Genomic offset using predicted genomic composition for present and future climate for several marker sets (all, random, random same allele frequencies, outlier LC, MC, CG, random_V2 and all_outliers)

### [13. GF genomic offset](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/GF_genomic_offset.html)

- GF GEA models
- Genomic offset for present and future climate for several marker sets (all, random, random same allele frequencies, outlier LC, MC, random_V2 and all_outliers)

### [14. Comparison genomic offset predictions](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Comparison_GO_predictions_Taxus_final_results.html)

- Comparison population genomic offset predictions across models and SNP sets
- Graphical visualisation

## Evaluation of the GEA models and the genomic offset predictions

### [15. Clonal bank genomic offset](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Genomic_offset_Clonal_bank.html)

RDA and GF genomic offsets for the clonal bank populations

### [16. Association fitness proxies ~ genomic offset predictions](https://thomas-francisco.github.io/Genomic-signatures-of-mal-adaptation-to-climate-in-English-Yew/HTML/Relationship_fitness_genomic_offset.html)

- Correlation across phenotypic traits
- Composite trait index
- Relationship fitness ~ genomic offset using:
    - Pearson correlation
    - Linear models (Inferential and Bayesian)
    - Quadratic models (Inferential and Bayesian)

# Sources

