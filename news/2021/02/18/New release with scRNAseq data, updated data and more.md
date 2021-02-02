This release, neXtProt data release 2021-??-??, is the 2021 reference for the [HUPO](https://www.hupo.org/) C-HPP project.

##Changes to the data

**New and updated data**

The data from HPA v20 have been integrated. N  new antibody-based data sets () are now included. The expression data now includes single-cell RNA-seq (scRNAseq) data. This new data is displayed in the RNA-seq HPA column, at the level of the evidences. A summary of the RNA-seq data is now included as well. Example: ?

This release also incorporates the latest PeptideAtlas human 2021-01 build. This build contains n new sample types (?), bringing the total to N sample types. Peptides from MassIVE (Mass Spectrometry Interactive Virtual Environment) have also been updated. A total of n peptides from ? tissue types have been integrated in this release. Taken together, this brings the number of natural peptides (seen by MS) to ?, up from 2524202 in the 2020 HUPO reference release.

Data from UniProtKB, GOA, IntAct, ENYO, GlyConnect and neXtProt have also been updated. The versions included in this release are found in the [release contents](../about/contents).

##Changes to the RDF data model
The predicates [:DomainInfo](https://snorql.nextprot.org/help/entity/DomainInfo) and [:PtmInfo](https://snorql.nextprot.org/help/entity/PtmInfo) were wrongly classified as :positionalAnnotation. They are now correctly classified as :generalAnnotation .

##New advanced search SPARQL queries

The following query has been added:

1. [NXQ\_00290](../proteins/search?mode=advanced&queryId=NXQ_00290) **Proteins that are enzymes requiring the cofactor Ca(2+) and with a calcium binding site**

The following queries have been modified to use the [IDSM](https://idsm.elixir-czech.cz/), Integrated Database of Small Molecules, SPARQL endpoint:

1. [NXQ\_00139]( ../proteins/search?mode=advanced&queryId=NXQ_00139) **Protein kinases which are high-confidence drug targets according to CHEMBL**
2. NXQ\_00266 **Proteins binding estradiol and/or similar molecules (substructure search with SMILES) and their associated GO_MF terms**
3. NXQ\_00267 **Proteins binding estradiol and/or similar molecules (similarity search with SMILES), and their associated GO_MF terms**

The latter two queries are found in the [SnorQL](https://snorql.nextprot.org/) interface.
