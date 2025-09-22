# Genomic signatures of climate-driven (mal)adaptation in an iconic conifer, the English yew (*Taxus baccata* L.)

English yew is a long-lived tree widely distributed in Europe from sea level up to 2200m, often forming small stands and/or isolated populations. Several studies have shown phenotypic differences among populations of English yew across climatic gradients, while others have found signatures of ongoing selection and identified climate-related genes. These evidences suggest that local adaptation to climate may occur across the distribution range of the English yew. Moreover, recent declines and local extinctions of this species in many parts of Europe could exacerbate the effects of climate change, particularly for Mediterranean populations at the warm and arid range limit, and for those in other sensitive environments, such as high-elevation mountain regions, where climate-induced stress is already being observed and/or is predicted to be particularly strong in the near future (Mendoza et al. 2009; Knight 2022). The main objectives of this study are i) to investigate patterns of local adaptation to climate in *T. baccata*, ii) to evaluate the potential of genomic offset to predict population maladaptation under novel climatic conditions for a species with a highly-fragmented distribution, and iii) to gain insight into the potential vulnerability of T. baccata populations to future climate by linking information on the current degree of local adaptation, the historical capacity of gene flow and the predicted future climate maladaptation. To meet these objectives, we first used climatic and genomic data from 29 populations across the species’ European range to identify gene-climate relationships, as well as candidate climate-associated loci; second, we computed the distance between the observed and predicted genomic composition to identify populations deviating  from average gene-climate relationships (subsequently called  ‘genomic discrepancy index’); and third, we calculated historical effective migration and genetic differentiation between populations to determine potential trends in gene flow capacity in the near future, assuming conservatism of historical patterns. Finally, we calculated genomic offsets using two methods and evaluated their predictions using phenotypic traits related to growth, growth phenology, reproductive phenology and drought/temperature tolerance, measured in plants from 26 populations grown in a comparative experiment. 

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

- Archambeau J, Benito-Garzón M, de-Miguel M, et al (2024) Evaluating genomic offset predictions in a forest tree with high population genetic structure. 2024.05.17.594631
- Auwera GAV der, O’Connor BD (2020) Genomics in the Cloud: Using Docker, GATK, and WDL in Terra. O’Reilly Media, Inc.
- Capblancq T, Forester BR (2021) Redundancy analysis: A Swiss Army Knife for landscape genomics. Methods in Ecology and Evolution 12:2298–2309. https://doi.org/10.1111/2041-210X.13722
- Caye K, Jumentier B, Lepeule J, François O (2019) LFMM 2: Fast and Accurate Inference of Gene-Environment Associations in Genome-Wide Studies. Molecular Biology and Evolution 36:852–860. https://doi.org/10.1093/molbev/msz008
- Ellis N, Smith SJ, Pitcher CR (2012) Gradient forests: calculating importance gradients on physical predictors. Ecology 93:156–168. https://doi.org/10.1890/11-0252.1
- Evanno G, Regnaut S, Goudet J (2005) Detecting the number of clusters of individuals using the software STRUCTURE: a simulation study. Mol Ecol 14:2611–2620. https://doi.org/10.1111/j.1365-294X.2005.02553.x
- Fitzpatrick MC, Chhatre VE, Soolanayakanahally RY, Keller SR (2021) Experimental support for genomic prediction of climate maladaptation using the machine learning approach Gradient Forests. Molecular Ecology Resources 21:2749–2765. https://doi.org/10.1111/1755-0998.13374
- Fitzpatrick MC, Keller SR (2015) Ecological genomics meets community-level modelling of biodiversity: mapping the genomic landscape of current and future environmental adaptation. Ecology Letters 18:1–16. https://doi.org/10.1111/ele.12376
- Forester BR, Lasky JR, Wagner HH, Urban DL (2018) Comparing methods for detecting multilocus adaptation with multivariate genotype–environment associations. Molecular Ecology 27:2215–2233. https://doi.org/10.1111/mec.14584
- Frichot E, Schoville SD, Bouchard G, François O (2013) Testing for associations between loci and environmental gradients using latent factor mixed models. Mol Biol Evol 30:1687–1699. https://doi.org/10.1093/molbev/mst063
- Gautier M (2015) Genome-Wide Scan for Adaptive Divergence and Association with Population-Specific Covariates. Genetics 201:1555–1579. https://doi.org/10.1534/genetics.115.181453
- Knight J (2022) Scientists’ warning of the impacts of climate change on mountains. PeerJ 10:e14253. https://doi.org/10.7717/peerj.14253
- Legendre P, Legendre L (2012) Chapter 11 - Canonical analysis. In: Legendre P, Legendre L (eds) Developments in Environmental Modelling. Elsevier, pp 625–710
- Marchi M, Bucci G, Iovieno P, Ray D (2024) ClimateDT: A Global Scale-Free Dynamic Downscaling Portal for Historic and Future Climate Data. Environments 11:82. https://doi.org/10.3390/environments11040082
- Mendoza I, Gómez‐Aparicio L, Zamora R, Matías L (2009) Recruitment limitation of forest communities in a degraded Mediterranean landscape. J Vegetation Science 20:367–376. https://doi.org/10.1111/j.1654-1103.2009.05705.x
- Oksanen J, Simpson GL, Blanchet FG, et al (2025) vegan: Community Ecology Package. 2.6-8
- Pritchard JK, Stephens M, Donnelly P (2000) Inference of Population Structure Using Multilocus Genotype Data. Genetics 155:945–959. https://doi.org/10.1093/genetics/155.2.945
- Santos AS, Gaiotto FA (2020) Knowledge status and sampling strategies to maximize cost-benefit ratio of studies in landscape genomics of wild plants. Sci Rep 10:3706. https://doi.org/10.1038/s41598-020-60788-8
- Tutorials: Quebec Center for Biodiversity Science (https://r.qcbs.ca/workshop10/book-en/redundancy-analysis.html) and Brenna R. Forester (https://bookdown.org/hhwagner1/LandGenCourse_book/WE_11.html)
- Matthew C. Fitzpatrick GitHub: https://github.com/fitzLab-AL/geneticOffsetR/blob/main/poplarGBS.gf.supportFunctions.R
