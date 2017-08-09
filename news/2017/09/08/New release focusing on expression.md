##RNASeq data integrated in neXtProt

To date, expression information at the level of the transcript in neXtProt came from microarray and expressed sequence tag (EST) data from Bgee. RNASeq data from Human Protein Atlas has been incorporated in this release. RNASeq data is highly accurate for quantifying expression levels with high reproducibility. Furthermore, a large dynamic range of transcript expression levels can be detected with a very low background signal. While RNASeq is quantitative, it is shown in the same semi-quantitative manner as the other data in the Expression view to make for easier comparison. 

This release also incorporates expression information and mutagenesis data from neXtProt, as well as updates of UniProtKB, Ensembl, IntAct, and GOA. 

##New rules to upgrade protein existence

The following rules have been implemented:

1.	Entries whose protein(s) existence is based on evidence at the transcript level, homology or a prediction (gene model) have been upgraded to evidence at the protein level if the entry has expression information or mutagenesis data from neXtProt.
2.	Entries whose protein(s) existence is based on homology or a prediction (gene model) in UniProtKB have been upgraded to evidence at the transcript level if the entry has medium or high expression by RNASeq. This new rule has been introduced so that the protein existence value is in synch with the RNASeq data in neXtProt.

A total of 17 entries have been upgraded to evidence at the protein level (PE1) and 106 entries to evidence at the transcript level (PE2).

##Revamped Expression view for entries

The Expression view provides information the expression of the entry in normal tissues. In addition to updating this page so that it loads more quickly, a number of changes have been implemented to improve usability:

1.	The new Table format shows the expression level for every tissue assayed.
2.	A new version of expression data incorporating the tissue hierarchy is now online. In this Ontology view, expression in a tissue is propagated to the parent term(s) so as to give a global picture of where the entry is expressed.
3.	The data shown in the TISSUE EXPRESSION section can now be exported in tab-delimited format.
