##Changes to the data

**New variant frequency data**

neXtProt data release 2019-08-08 incorporates the exome data from Genome Aggregation Database ([gnomAD]( https://gnomad.broadinstitute.org/)). In this release, m entries (%) and n variants (%) have frequency data from gnomAD. As multiple genomic variants can give rise to the same variant at the protein level, the gnomAD data is provided at the evidence level. Specifically, we display the _Allele frequency_, including the _allele count_ and _allele number_, as well as the _Number of homozygotes_.

Both the neXtProt data model and the XML have been adapted to include this new data. In the data model, the allele frequency, allele count, allele number and homozygote count have been added in the [Evidence](https://snorql.nextprot.org/help/entity/Evidence). The changes in the XML are described in the XSD file available at [ftp://ftp.nextprot.org/pub/current\_release/xml/nextprot-export-v2.xsd](ftp://ftp.nextprot.org/pub/current_release/xml/nextprot-export-v2.xsd).

**Data updated**

Glycosylation sites from GlyConnect have been updated. There are now glycosylation sites for 1154 entries, including 107 new entries, in this release.

Additional annotations by neXtProt have also been integrated. Phenotype annotations are now available for an additional 17 entries, including cellular tumor antigen p53 (TP53) [NX\_P04637](../entry/NX_P04637/phenotypes).

##Changes to tools

**New protein digestion tool**

In order to help scientists determine which enzymes and experimental conditions might yield peptides that could be used to confidently identify a protein of interest, we have developed the [protein digestion tool](../tools/protein-digestion). For a specific isoform and digestion conditions, the tool returns the number of peptides and the number of unique peptides obtained for 27 proteases and digestion conditions. Upon selecting a specific protease or condition, the tool returns all the expected peptides. The following information is provided for each peptide: sequence, length, position of the peptide in the isoform sequence, number of miscleavages, whether the peptide is unique to the entry without taking into account variants, and whether the peptide is in neXtProt, either as a natural “Peptide” feature or a synthetic “SRM Peptide” feature. To facilitate the comparison of the results with the peptide data in neXtProt, a link to the Peptide view for the isoform is provided.

The tables showing the results of the summary of the digestion with all proteases and conditions, as well as that showing the peptides for the digestion with the specified protease or condition, were designed for ease of use. A text search allows the desired result to be found rapidly. It is also possible to sort the contents of all columns. Finally, for the table showing the resulting peptides, filters are available to retrieve peptides matching any criteria.

**Changes to the peptide uniqueness checker**

The Peptide uniqueness checker in our [user interface](../tools/peptide-uniqueness-checker) and [API](https://api.nextprot.org/) returned the error message “Impossible to get the data” for 6 AA polyX peptides. This issue has been fixed.  Checking the uniqueness of peptide HHHHHH, found in Isoform 1 of POU domain, class 3, transcription factor 1 (NX_Q03052) at positions 439-444, now returns this entry.

A POST option has been added to the peptide uniqueness checker on our API to be able to handle large numbers of peptides.

**New community tool**

_TEXT from Lydie_

##Changes to advanced search SPARQL queries

The following queries have been added:

1. NXQ\_00250 **Proteins that act as transporters and their TCDB numbers** in the [SnorQL](https://snorql.nextprot.org/) interface
2. [NXQ\_00251](../proteins/search?mode=advanced&queryId=NXQ_00251) **Proteins with at least one proteotypic peptide 9aa+ not mapping on canonical isoform**
3. NXQ\_00253 **Human pathways in which at least one protein is mitochondrial GOLD** in the [SnorQL](https://snorql.nextprot.org/) interface
4. 

The following query has been simplified:

1. [NXQ\_00103](../proteins/search?mode=advanced&queryId=NXQ_00103)  Proteins that do not have a cross-reference to an Ensembl ENSG
