##Changes to the data

**Updated expression data from Bgee**

This release, neXtProt data release 2020-10-??, integrates expression data from Bgee 14.1. [Bgee](https://bgee.org/) is a database to retrieve and compare gene expression patterns in multiple animal species described in the recent preprint by [Bastian FB _et al._](https://www.biorxiv.org/content/10.1101/2020.05.28.119560v4)

To date, expression information from Bgee came from Affymetrix microarray and expressed sequence tag (EST) data. RNA-seq data from Bgee has been incorporated in this release. In order to distinguish it from the HPA RNA-seq data set, it is displayed in a separate column in the entry Expression view. Example: 

A total of ? expression profile annotations involving ? entries were integrated from Bgee in this release. There are ? entries with EST data, ? entries with microarray data and ? entries with RNA-seq data from Bgee.

**Updated interaction data from IntAct**

Binary interaction data describing protein-protein interactions (PPI) from IntAct has also been updated. [IntAct](https://www.ebi.ac.uk/intact/) provides the experimental method using the PSI Molecular Interactions (PSI-MI) controlled vocabulary and the publication. In order to reduce the redundancy in the evidences, the most precise PSI-MI term has been retained when an interaction from a publication has been curated by IntAct using multiple PSI-MI terms. Both the PSI-MI and publications are now displayed. Example: 

A total of ? binary interactions involving ? entries and ? interactors manually curated from ? publications by IntAct were integrated in this release.

##Changes to the PE upgrade rules

Following the integration of RNA-seq data from Bgee, the following rule is now implemented:

_Entries whose protein(s) existence is based on evidence from homology (PE3) or a prediction (gene model) (PE4) are upgraded to evidence at the transcript level (PE2) if the entry has an expression profile annotation with evidence of quality GOLD with RNA-seq evidence (ECO:0000295) and expression level detected._

##Changes to the export files

**New mapping file**

The integration of the Bgee data required a new mapping file. This file maps combinations of UBERON anatomical structure terms and developmental stage terms from Bgee to the caloha vocabulary developed and used in neXtProt. The new mapping file is found at [ftp://ftp.nextprot.org/pub/current\_release/mapping/](ftp://ftp.nextprot.org/pub/current_release/mapping/) 

The FTP [README file](ftp://ftp.nextprot.org/pub/README) at has been updated to include the new mapping file.

##Changes to advanced search SPARQL queries

The following new query has been added to illustrate the use of PSI-MI terms:
1. [NXQ\_00287](../proteins/search?mode=advanced&queryId=NXQ_00287) **Proteins with interactions obtained from x-ray crystallography**
