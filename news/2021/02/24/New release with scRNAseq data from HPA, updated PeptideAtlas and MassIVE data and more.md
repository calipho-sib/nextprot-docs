This release, neXtProt data release 2021-02-18, is the 2021 reference for the [HUPO](https://www.hupo.org/) C-HPP project.

##Changes to the data

**New data**

The data from HPA version 20 have been integrated. The expression data now includes single-cell RNA-seq (scRNAseq) data. This new data is found in the RNA-seq HPA column and is displayed at the level of the evidences. A textual summary of the RNA-seq data is now included as well. Example: FUN14 domain-containing protein 1 (FUNDC1) [NX_Q8IVP5](../entry/NX_Q8IVP5/expression)

**Updated data**

This release also incorporates the latest PeptideAtlas human 2021-01 build. Peptides from MassIVE (Mass Spectrometry Interactive Virtual Environment) have also been updated. Taken together, this brings the number of natural peptides (seen by MS) to 2726064, up from 2524202 in the 2020 HUPO reference release.

Data from UniProtKB, GOA, GlyConnect and neXtProt have also been updated. The versions included in this release are found in the [release contents](../about/contents).

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
