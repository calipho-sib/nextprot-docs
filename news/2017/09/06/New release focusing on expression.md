This release incorporates expression information and mutagenesis data from neXtProt, as well as updates of UniProtKB, Human Protein Atlas, Ensembl, IntAct, and GOA.

##RNA-seq data integrated in neXtProt

To date, expression information at the level of the transcript in neXtProt came from microarray and expressed sequence tag (EST) data from Bgee. RNA-seq data from Human Protein Atlas has been incorporated in this release. RNA-seq data is highly accurate for quantifying expression levels with high reproducibility. Furthermore, a large dynamic range of transcript expression levels can be detected with a very low background signal. While RNA-seq is quantitative, it is shown in the same semi-quantitative manner as the other data in the Expression view to make for easier comparison. 

##Revamped Expression view for entries

The Expression view provides information the expression of the entry in normal tissues. The following changes have been implemented to improve usability:

1.	The new Tabular view shows the expression level for every tissue assayed.
2.	The Ontological view showing the expression data while allowing the tissue hierarchy to be explored has been improved. In this view, expression in a tissue is also shown in the parent term(s) so as to give a global picture of where the entry is expressed.
3.	A new export functionality allows all the experimental expression data for the entry to be downloaded in tab-delimited format.

##Revamped Sequence view for entries

In the Sequence view, information concerning sequence features applying to the isoform selected is displayed. A new search of the positional annotations listed in the feature table has been implemented. Searching for a category of feature or for text found in the description allows the user to rapidly view these in the table.

##New rules to upgrade protein existence

The following rules have been implemented:

1.	Entries whose protein(s) existence is based on evidence at the transcript level, homology or a prediction (gene model) have been upgraded to evidence at the protein level if the entry has expression information or mutagenesis data from neXtProt.
2.	Entries whose protein(s) existence is based on homology or a prediction (gene model) in UniProtKB have been upgraded to evidence at the transcript level if the entry has medium or high expression by RNA-seq. This new rule has been introduced so that the protein existence value is in synch with the RNA-seq data in neXtProt.

A total of 17 entries have been upgraded to evidence at the protein level (PE1) and 106 entries to evidence at the transcript level (PE2).

##Changes to the FTP site

As UniProtKB has extended their controlled vocabulary for PTM to include glycosylation sites, the neXtProt vocabulary for carbohydrate modifications is no longer used. The file cv\_carbohydrate.txt has been removed from [ftp://ftp.nextprot.org/pub/current\_release/controlled_vocabularies/](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/).
