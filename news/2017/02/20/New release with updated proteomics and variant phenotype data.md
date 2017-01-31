**neXtProt release 2017-01-23**

**Changes to the data**

The main focus of this release is proteomics as this release is the 2017 reference for the HUPO C-HPP project. Specifically, data from the following sources has been updated:

1. **PeptideAtlas** The new Human 2017-01 build has been integrated. The number of peptides mapping to entries now cover ?% of the entries in the release. Furthermore, the Phosphoproteome data has been updated. As usual, we only integrate phosphorylation sites with a PTM score >0.95, with those having a PTM score >0.99 labelled as gold. 
2. **SRMAtlas** The latest build, Human 2016-04, has been integrated; there are now SRM peptides for ?% of the entries.

The neXtProt variant phenotype annotations have been updated both in the neXtProt entry Phenotype view, as well as in the Portals:

1.	**neXtProt Phenotype view** All entries with variant phenotype annotations in the Portals now have a corresponding Phenotype view. In particular, the following entries now have variant phenotype data: BRCA2, EPCAM, MLH1, MLH3, MSH2, MSH6, PMS2. 
2.	**Portals** (see NEXTPROT-1187)

??? Are there discrepancies between the data in the Phenotype view and that in the portals?

In addition, this release includes updates of GOA, IntAct and UniProtKB/Swiss-Prot.

**Changes to the tools**

neXtProt tools (BLAST and pepx) are now found in a separate section of the API and their documentation has been updated.
