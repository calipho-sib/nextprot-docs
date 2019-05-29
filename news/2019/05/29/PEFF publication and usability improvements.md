##Publication describing PEFF

The PEFF files available from neXtProt comply with the format described in:

Binz PA, Shofstahl J, Vizcaíno JA, Barsnes H, Chalkley RJ, Menschaert G, Alpi E, Clauser K, Eng JK, Lane L, Seymour SL, Sánchez LFH, Mayer G, Eisenacher M, Perez-Riverol Y, Kapp EA, Mendoza L, Baker PR, Collins A, Van Den Bossche T, Deutsch EW.
**Proteomics Standards Initiative Extended FASTA Format (PEFF)**
J Proteome Res. 2019 May 13. doi: [10.1021/acs.jproteome.9b00064](https://doi.org/10.1021/acs.jproteome.9b00064). PMID: [31081335](https://www.ncbi.nlm.nih.gov/pubmed/31081335)

Please cite this publication if you are using the PEFF files.

##Changes to improve usability

The following changes have been implemented:

1.	[Peptide uniqueness checker](../tools/peptide-uniqueness-checker). In response to user requests, we have added a brief description of what the tool does, an example and icons in the match results. Color blind users will now be able to distinguish whether peptides are "unique", "pseudo-unique" or "not unique".
2.	[Portals](../portals/navmut). The entry accession (AC) corresponding to the annotation subject has been added. It is now possible to determine the list of entries with data in the portal by downloading the contents and removing duplicates in the column with the entry AC.
3.	Expression view for entries. We have fixed a bug in the display of the expression data and the tooltip text in the Tabular view. This view shows the expression level for every tissue assayed. Example: Insulin (INS) [NX\_P01308](../entry/NX_P01308/expression)
4.	Publication pages. These now load more quickly.

##Changes to advanced search SPARQL queries

The following query has been added:

1.	NXQ\_00248 **Variants with phenotype annotation that map to a 3D structure** in the [SNORQL](https://snorql.nextprot.org/) interface

The following query has been modified as it gave incorrect results:

1.	NXQ\_00229 **Proteins with 2 peptides from only one PeptideAtlas data set** in the [SNORQL](https://snorql.nextprot.org/) interface
