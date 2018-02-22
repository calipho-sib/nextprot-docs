##Changes to the data

This release, neXtProt data release 2018-01-17, is the 2018 reference for [HUPO](https://www.hupo.org/). This release incorporates the latest [PeptideAtlas](http://www.peptideatlas.org/) release (Human 2018-01). A total of 51 PeptideAtlas data sets, which include data from cancer tissues and cell lines, with over 1.4 million peptides detected by mass spectrometry have been integrated.

Data from UniProtKB, Ensembl, IntAct, GOA, as well as GeneIDs, have also been updated. The data have been supplemented with GO molecular function, biological process and cellular component annotations for most of the human protein kinases, as well as expression information, mutagenesis and variant phenotype data from neXtProt.

##New rules to upgrade protein existence

The following rule has been implemented: Entries whose protein(s) existence is based on evidence at the transcript level, homology or a prediction (gene model) have been upgraded to evidence at the protein level if the entry has GOLD binary interaction data from neXtProt.

##Revamped Proteomics view for entries

The Proteomics view provides information useful to the proteomics community. In particular, this view displays peptides from PeptideAtlas and neXtProt observed by mass spectrometry and SRM peptides from SRMAtlas. It also shows the epitopes recognized by antibodies from the Human protein atlas.

It is now possible to search the positional annotations listed in the feature table for a specific category or for text found in the feature description. For instance, searching for "SRM" returns the number of SRM peptides mapping to the isoform and allows one to rapidly browse the data for all SRM peptides.

To be consistent with the changes implemented in the Peptide uniqueness checker, peptides mapping to entries with identical isoform sequences are now described as being "Pseudo-unique" rather than "Found in other entries".

##Advanced search SPARQL queries

The following queries have been added: 

1. NXQ_00225 **Proteins with high proline content** in the [SnorQL](https://snorql.nextprot.org/) interface
2. [NXQ\_00226](../proteins/search?mode=advanced&queryId=NXQ_00226) **Proteins with at least 2 validating peptides >=9aa found in blood plasma, urine or cerebrospinal fluid** to retrieve potential markers
3. [NXQ_00230](../proteins/search?mode=advanced&queryId=NXQ_00230) **Proteins with experimentally determined lengthy alpha-helices (> 75 aa)** illustrating querying for proteins with specific secondary structure

##Change to the licence applying to the use of our data available from our FTP site

neXtProt downloadable data files used to be available under the Creative Commons Attribution-NoDerivs 
License. As of this release, they are available under the [Creative Commons Attribution 4.0
International Public License](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0). 
