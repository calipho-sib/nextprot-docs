## Changes to the data

Subcellular localization and expression data (at RNA and protein levels) from [HPA](https://www.proteinatlas.org/) version 23 has now been integrated. 
As a result from RNAseq data integration, 37 entries whose protein(s) existence was based on homology (PE3) or on a prediction (gene model) (PE4) are now scored PE2 (protein(s) existence based on evidence at transcript level).

## Changes to the user interface
The peptide uniqueness checker has been improved so that longer lists of peptides can be processed (up to 1000 peptides of any length).

## Changes to the SPARQL queries

The following federated query did not work anymore (time out) and has been removed:

*	NXQ\_00273 **Proteins involved in coronaviruses/SARS-CoV-2 pathways that are expressed in lung according to RNA-seq analysis and detected at high levels by IHC in at least one lung cell type**
