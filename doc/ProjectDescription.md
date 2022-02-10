Introduction
============

The freshwater cnidarian *Hydra* coexists with a rich diversity of
host-associated microbes. These microbes colonize external epithelial
surfaces (Fraune et al.
([2015](#ref-frauneBacteriaBacteriaInteractions2015)) Deines and Bosch
([2016](#ref-deinesTransitioningMicrobiomeComposition2016))), inhabit
intercellular spaces (Rathje et al.
([2020](#ref-rathjeDynamicInteractionsHostassociated2020))), and in some
species can even occur inside cells as endosymbionts (Fraune and Bosch
([2007](#ref-frauneLongtermMaintenanceSpeciesspecific2007))). The
*Hydra* microbiota has diverse effects on the host. Animals with their
microbiota experimentally removed have reduced movement and
contractility (Murillo-Rincon et al.
([2017](#ref-murillo-rinconSpontaneousBodyContractions2017))) and
impaired ability to reproduce asexually (Rahat and Dimentman
([1982](#ref-rahatCultivationBacteriaFreeHydra1982))). Interactions
between microbial components influence pattern formation (Taubenheim et
al. ([2020](#ref-taubenheimBacteriaTemperatureregulatedPeptides2020))),
and can induce tumor development (Rathje et al.
([2020](#ref-rathjeDynamicInteractionsHostassociated2020))), but the
presence of core microbial elements also protects the host against
fungal infections (Fraune et al.
([2015](#ref-frauneBacteriaBacteriaInteractions2015))).

*Hydra* polyps actively shape the composition of their associated
bacterial community through the secretion of antimicrobial peptides
(Fraune et al. ([2010](#ref-frauneEarlyBranchingMetazoan2010)), S.
Franzenburg et al.
([2013](#ref-franzenburgDistinctAntimicrobialPeptide2013)), Augustin et
al. ([2017](#ref-augustinSecretedAntibacterialNeuropeptide2017))). As a
result, laboratory maintained *Hydra* species differ in the bacterial
community (S. Franzenburg et al.
([2013](#ref-franzenburgDistinctAntimicrobialPeptide2013))), and show
long-term association with the host, partly reflecting differences
observed in their natural habitats (Fraune and Bosch
([2007](#ref-frauneLongtermMaintenanceSpeciesspecific2007))).
Furthermore, components of the microbiota are at least partly
transmitted vertically to embryos through a process controlled by
maternal antimicrobial peptides (Fraune et al.
([2010](#ref-frauneEarlyBranchingMetazoan2010)), Franzenburg et al.
([2013](#ref-franzenburgBacterialColonizationHydra2013))), providing an
opportunity for coevolution between host physiology and microbial
diversity. However, factors driving variation in the microbial
composition and diversity of natural *Hydra* populations remained so far
unexplained.

In a current study we aimed to understand the factors that shape
bacterial diversity in natural *Hydra* populations. To this end, we
collected *Hydra* polyps belonging to three different co-existing
species (*H. oligactis*, *H. vulgaris* and *H. circumcincta*) from 21
Central European locations. We asked whether bacterial diversity in
*Hydra* is affected by 1) sampling population ID, 2) water body type 3)
nutrient load of sampling population, 4) host species, and 5) host
reproductive state. In line with previous studies (e.g. Fraune and Bosch
([2007](#ref-frauneLongtermMaintenanceSpeciesspecific2007))) we
predicted that the three *Hydra* species will be associated with
distinct microbial communities and were interested in finding out how
consistent these species differences are across a range of distinct
populations. Furthermore, we hypothesized that the type of habitat could
influence the microbial diversity from which host-associated microbial
communities are assembled and therefore recorded, for each location,
whether it was standing or flowing water and categorized them in terms
of nutrient load: meso-eutrophic, eutrophic or hyper-eutrophic. Finally,
we hypothesized that life history stage of the host (specifically,
whether it was reproducing sexually or asexually) can affect the
diversity of microbial taxa associated with the host because of the
altered physiology associated with sexual reproduction. In at least one
of the three species (H. oligactis), sexual reproduction is associated
with marked reductions in somatic maintenance functions, including loss
of regeneration ability, stem cell depletion and disappearance of
nematocytes (stinging cells) important for food capture (Sebestyén,
Barta, and Tökölyi ([2018](#ref-sebestyenReproductiveModeStem2018))),
and these physiological changes could also affect the ability to
regulate host-associated microbes.

We found that the sampling site (population) has the strongest effect on
α-and β-diversity, followed by the type of the water body, while the
host factors (species and reproduction mode) had a much weaker, but
consistent effect on the bacterial diversities. The results showed that
environmental factors were most strongly associated with changes in the
microbial community while the bacterial communities still specifically
reflect the host species.

The aim of this small project is the evaluation of the metabolic
capabilities of wild type *Hydra* bacteria using picrust2 Douglas et al.
([2020](#ref-douglasPICRUSt2PredictionMetagenome2020)) and comparing the
results to the bacterial diversity.

Data
====

In this repository you will find a `data/` directory which contains
following files:

-   A fasta file for the 16S sequences for each ESV of the study
-   A table with taxonomic annotations for the different 16S sequences
-   A matrix containing the raw read counts for each sample (columns)
    and ESV (rows)
-   An annotation file for each sample (what species, sampling site
    etc.)

Anticipated outcome
===================

1.  Use the data to predict enzymatic activity of each ESV using
    [picrust2](https://github.com/picrust/picrust2/wiki/)
    1.  Predict KEGG, NOG and EC numbers for each ESV
    2.  Keep intermediate files for reproducibility
    3.  Determine the number of ESVs where no prediction could be made
        per sample. Think of a good way to plot these numbers, once
        weighted and unweighted by ESV abundance
2.  Predict pathway abundances per sample using
    [picrust2](https://github.com/picrust/picrust2/wiki/)
3.  Analyse *α*- and *β*-diversity measures (Shannon and Bray-Curtis)
    for the Pathway abundances
    1.  Create boxplots showing differences in Shannon diversity for
        Species, Sampling Site (PopID), Nutritional level of the water
        body and water body type.
    2.  Calculate PC-Analysis on the *β*-diversity measures, plot the
        first 3 principal components in scatter plots against each
        other. Create versions of the plot where the color of the dots
        indicate Species, Sampling Site (PopID), Nutritional level of
        the water body and water body type.
4.  Keep track and comment on all analysis steps for reproducibility

Help
----

Help can be found by contacting us on the slack channel.

Here some hints for performing the analysis:

### Predicting metabolic function from 16S data

[picrust2](https://github.com/picrust/picrust2/wiki) is used for
metabolic function prediction from 16S data. For the original
publication see here: Langille et al.
([2013](#ref-langillePredictiveFunctionalProfiling2013)) and Douglas et
al. ([2020](#ref-douglasPICRUSt2PredictionMetagenome2020))

For data analysis we usually refer to R. Specifically here are some
packages to have a look at

-   [data.table](https://github.com/cran/data.table) for data
    manipulation
-   [ggplot2](https://ggplot2.tidyverse.org/) for plotting
-   [vegan](https://peat-clark.github.io/BIO381/veganTutorial.html) for
    basic ecological analysis
-   [phyloseq](https://joey711.github.io/phyloseq/) for advanced
    ecological analysis - specialized to 16S sequencing data

References
==========

Augustin, René, Katja Schröder, Andrea P. Murillo Rincón, Sebastian
Fraune, Friederike Anton-Erxleben, Eva-Maria Herbst, Jörg Wittlieb, et
al. 2017. “A Secreted Antibacterial Neuropeptide Shapes the Microbiome
of Hydra.” *Nature Communications* 8 (1): 698.
<https://doi.org/10.1038/s41467-017-00625-1>.

Deines, Peter, and Thomas C. G. Bosch. 2016. “Transitioning from
Microbiome Composition to Microbial Community Interactions: The
Potential of the Metaorganism Hydra as an Experimental Model.”
*Frontiers in Microbiology* 7 (October).
<https://doi.org/10.3389/fmicb.2016.01610>.

Douglas, Gavin M., Vincent J. Maffei, Jesse R. Zaneveld, Svetlana N.
Yurgel, James R. Brown, Christopher M. Taylor, Curtis Huttenhower, and
Morgan G. I. Langille. 2020. “PICRUSt2 for Prediction of Metagenome
Functions.” *Nature Biotechnology* 38 (6): 685–88.
<https://doi.org/10.1038/s41587-020-0548-6>.

Franzenburg, Sören, Sebastian Fraune, Philipp M Altrock, Sven Künzel,
John F Baines, Arne Traulsen, and Thomas CG Bosch. 2013. “Bacterial
Colonization of Hydra Hatchlings Follows a Robust Temporal Pattern.”
*The ISME Journal* 7 (4): 781–90.
<https://doi.org/10.1038/ismej.2012.156>.

Franzenburg, S., J. Walter, S. Kunzel, J. Wang, J. F. Baines, T. C. G.
Bosch, and S. Fraune. 2013. “Distinct Antimicrobial Peptide Expression
Determines Host Species-Specific Bacterial Associations.” *Proceedings
of the National Academy of Sciences* 110 (39): E3730–E3738.
<https://doi.org/10.1073/pnas.1304960110>.

Fraune, S., R. Augustin, F. Anton-Erxleben, J. Wittlieb, C. Gelhaus, V.
B. Klimovich, M. P. Samoilovich, and T. C. G. Bosch. 2010. “In an Early
Branching Metazoan, Bacterial Colonization of the Embryo Is Controlled
by Maternal Antimicrobial Peptides.” *Proceedings of the National
Academy of Sciences* 107 (42): 18067–72.
<https://doi.org/10.1073/pnas.1008573107>.

Fraune, S., and T. C. G. Bosch. 2007. “Long-Term Maintenance of
Species-Specific Bacterial Microbiota in the Basal Metazoan Hydra.”
*Proceedings of the National Academy of Sciences* 104 (32): 13146–51.
<https://doi.org/10.1073/pnas.0703375104>.

Fraune, Sebastian, Friederike Anton-Erxleben, René Augustin, Sören
Franzenburg, Mirjam Knop, Katja Schröder, Doris Willoweit-Ohl, and
Thomas CG Bosch. 2015. “BacteriaBacteria Interactions Within the
Microbiota of the Ancestral Metazoan Hydra Contribute to Fungal
Resistance.” *The ISME Journal* 9 (7): 1543–56.
<https://doi.org/10.1038/ismej.2014.239>.

Langille, Morgan G I, Jesse Zaneveld, J Gregory Caporaso, Daniel
McDonald, Dan Knights, Joshua A Reyes, Jose C Clemente, et al. 2013.
“Predictive Functional Profiling of Microbial Communities Using 16S rRNA
Marker Gene Sequences.” *Nature Biotechnology* 31 (9): 814–21.
<https://doi.org/10.1038/nbt.2676>.

Murillo-Rincon, Andrea P., Alexander Klimovich, Eileen Pemöller, Jan
Taubenheim, Benedikt Mortzfeld, René Augustin, and Thomas C. G. Bosch.
2017. “Spontaneous Body Contractions Are Modulated by the Microbiome of
Hydra.” *Scientific Reports* 7 (1): 15937.
<https://doi.org/10.1038/s41598-017-16191-x>.

Rahat, M., and Ch. Dimentman. 1982. “Cultivation of Bacteria-Free
*Hydra* *Viridis* : Missing Budding Factor in Nonsymbiotic Hydra.”
*Science* 216 (4541): 67–68. <https://doi.org/10.1126/science.7063873>.

Rathje, Kai, Benedikt Mortzfeld, Marc P. Hoeppner, Jan Taubenheim,
Thomas C. G. Bosch, and Alexander Klimovich. 2020. “Dynamic Interactions
Within the Host-Associated Microbiota Cause Tumor Formation in the Basal
Metazoan Hydra.” Edited by Fanxiu Zhu. *PLOS Pathogens* 16 (3):
e1008375. <https://doi.org/10.1371/journal.ppat.1008375>.

Sebestyén, Flóra, Zoltán Barta, and Jácint Tökölyi. 2018. “Reproductive
Mode, Stem Cells and Regeneration in a Freshwater Cnidarian with
Postreproductive Senescence.” Edited by David Reznick. *Functional
Ecology* 32 (11): 2497–2508. <https://doi.org/10.1111/1365-2435.13189>.

Taubenheim, Jan, Doris Willoweit-Ohl, Mirjam Knop, Sören Franzenburg,
Jinru He, Thomas C. G. Bosch, and Sebastian Fraune. 2020. “Bacteria- and
Temperature-Regulated Peptides Modulate *β*-Catenin Signaling in
*Hydra*.” *Proceedings of the National Academy of Sciences* 117 (35):
21459–68. <https://doi.org/10.1073/pnas.2010945117>.
