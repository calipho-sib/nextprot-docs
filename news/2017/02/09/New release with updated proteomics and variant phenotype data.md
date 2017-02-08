**neXtProt release 2017-01-23**

**Changes to the data**

The main focus of this release is proteomics as this release is the 2017 reference for the HUPO C-HPP project. Specifically, data from the following sources has been updated:

1. **PeptideAtlas** The new Human 2017-01 build has been integrated. An additional 58592 peptides from PeptideAtlas have been integrated compared to the previous release. The number of peptides mapping to entries now cover 88% of the entries in the release. Furthermore, the Phosphoproteome data has been updated. As usual, we only integrate phosphorylation sites with a PTM score >0.95, with those having a PTM score >0.99 labelled as gold. 
2. **SRMAtlas** The latest build, Human 2016-04, has been integrated; there are now SRM peptides for 98.6% of the entries.

The variant phenotype annotations from the neXtProt team have been updated both in the neXtProt entry Phenotype view, as well as in the Portals. In particular, data for the following entries has been incorporated in the Cancer variants portal: BRCA2, EPCAM, MLH1, MLH3, MSH2, MSH6, PMS2. The portals now contain two additional columns labeled **Cell line / Tissue** and **Experimental details** providing more details concerning the experimental context. 

In addition, this release includes updates of GOA, IntAct and UniProtKB/Swiss-Prot.

**Changes to the tools**

neXtProt tools (BLAST and Peptide unicity checker) are now found in a separate section of the API and their documentation has been updated.
