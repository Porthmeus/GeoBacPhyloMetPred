---
title: Predicting metabolic function in _Hydra microbiome
output: html_document
#    rmdformats::downcute:
#        highlight: tango
#        use_bookdown: TRUE
bibliography: ["bib/Library.bib"]
link-citations: true
---

# Introduction

The freshwater cnidarian _Hydra coexists with a rich diversity of host-associated microbes. These microbes colonize external epithelial surfaces @frauneBacteriaBacteriaInteractions2015 @deinesTransitioningMicrobiomeComposition2016, inhabit intercellular spaces @rathjeDynamicInteractionsHostassociated2020, and in some species can even occur inside cells as endosymbionts @frauneLongtermMaintenanceSpeciesspecific2007. The _Hydra microbiota has diverse effects on the host. Animals with their microbiota experimentally removed have reduced movement and contractility @murillo-rinconSpontaneousBodyContractions2017 and impaired ability to reproduce asexually @rahatCultivationBacteriaFreeHydra1982. Interactions between microbial components influence pattern formation @taubenheimBacteriaTemperatureregulatedPeptides2020, and can induce tumor development @rathjeDynamicInteractionsHostassociated2020, but the presence of core microbial elements also protects the host against fungal infections @frauneBacteriaBacteriaInteractions2015. 

_Hydra polyps actively shape the composition of their associated bacterial community through the secretion of antimicrobial peptides (@frauneEarlyBranchingMetazoan2010, @franzenburgDistinctAntimicrobialPeptide2013, @augustinSecretedAntibacterialNeuropeptide2017). As a result, laboratory maintained _Hydra species differ in the bacterial community @franzenburgDistinctAntimicrobialPeptide2013, and show long-term association with the host, partly reflecting differences observed in their natural habitats @frauneLongtermMaintenanceSpeciesspecific2007. Furthermore, components of the microbiota are at least partly transmitted vertically to embryos through a process controlled by maternal antimicrobial peptides (@frauneEarlyBranchingMetazoan2010, @franzenburgBacterialColonizationHydra2013), providing an opportunity for coevolution between host physiology and microbial diversity. However, factors driving variation in the microbial composition and diversity of natural _Hydra populations remained so far unexplained.

In a current study we aimed to understand the factors that shape bacterial diversity in natural Hydra populations. To this end, we collected Hydra polyps belonging to three different co-existing species (H. oligactis, H. vulgaris and H. circumcincta) from 21 Central European locations. We asked whether bacterial diversity in Hydra is affected by 1) sampling population ID, 2) water body type 3) nutrient load of sampling population, 4) host species, and 5) host reproductive state. In line with previous studies (e.g. @frauneLongtermMaintenanceSpeciesspecific2007) we predicted that the three Hydra species will be associated with distinct microbial communities and were interested in finding out how consistent these species differences are across a range of distinct populations. Furthermore, we hypothesized that the type of habitat could influence the microbial diversity from which host-associated microbial communities are assembled and therefore recorded, for each location, whether it was standing or flowing water and categorized them in terms of nutrient load: meso-eutrophic, eutrophic or hyper-eutrophic. Finally, we hypothesized that life history stage of the host (specifically, whether it was reproducing sexually or asexually) can affect the diversity of microbial taxa associated with the host because of the altered physiology associated with sexual reproduction. In at least one of the three species (H. oligactis), sexual reproduction is associated with marked reductions in somatic maintenance functions, including loss of regeneration ability, stem cell depletion and disappearance of nematocytes (stinging cells) important for food capture @sebestyenReproductiveModeStem2018, and these physiological changes could also affect the ability to regulate host-associated microbes. 

We found that the sampling site (population) has the strongest effect on α-and β-diversity, followed by the type of the water body, while the host factors (species and reproduction mode) had a much weaker, but consistent effect on the bacterial diversities. The results showed that environmental factors were most strongly associated  with changes in the microbial community  while the bacterial communities still specifically reflect the host species.

The aim of this small project is the evaluation of the metabolic capabilities of wild type _Hydra_ bacteria using picrust2 @douglasPICRUSt2PredictionMetagenome2020 and comparing the results to the bacterial diversity.

# Data

In this repository you will find a `data/` directory which contains following files:

+ A fasta file for the 16S sequences for each ESV of the study
+ A table with taxonomic annotations for the different 16S sequences
+ A matrix containing the raw read counts for each sample (columns) and ESV (rows)
+ An annotation file for each sample (what species, sampling site etc.)

# Anticipated outcome

1. Use the data to predict enzymatic activity of each ESV using [picrust2](https://github.com/picrust/picrust2/wiki/)
    1. Predict KEGG, NOG and EC numbers for each ESV
    2. Keep intermediate files for reproducibility
    3. Determine the number of ESVs where no prediction could be made per sample. Think of a good way to plot these numbers, once weighted and unweighted by ESV abundance
2. Predict pathway abundances per sample using [picrust2](https://github.com/picrust/picrust2/wiki/)
3. Analyse $\alpha$- and $\beta$-diversity measures (Shannon and Bray-Curtis) for the Pathway abundances
    1. Create boxplots showing differences in Shannon diversity for Species, Sampling Site (PopID), Nutritional level of the water body and water body type.
    2. Calculate PC-Analysis on the $\beta$-diversity measures, plot the first 3 principal components in scatter plots against each other. Create versions of the plot where the color of the dots indicate Species, Sampling Site (PopID), Nutritional level of the water body and water body type.
4. Keep track and comment on all analysis steps for reproducibility

## Help

Help can be found by contacting us on the slack channel.

Here some hints for performing the analysis:

### Predicting metabolic function from 16S data

[picrust2](https://github.com/picrust/picrust2/wiki) is used for metabolic function prediction from 16S data. For the original publication see here: @langillePredictiveFunctionalProfiling2013 and @douglasPICRUSt2PredictionMetagenome2020

For data analysis we usually refer to R. Specifically here are some packages to have a look at

+ [data.table](https://github.com/cran/data.table) for data manipulation
+ [ggplot2](https://ggplot2.tidyverse.org/) for plotting
+ [vegan](https://peat-clark.github.io/BIO381/veganTutorial.html) for basic ecological analysis
+ [phyloseq](https://joey711.github.io/phyloseq/) for advanced ecological analysis - specialized to 16S sequencing data




