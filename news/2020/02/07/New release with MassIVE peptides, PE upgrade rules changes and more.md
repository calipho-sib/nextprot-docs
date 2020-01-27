This latest release, neXtProt data release 2020-01-17, is the 2020 reference for the [HUPO](https://www.hupo.org/) C-HPP project.

##Changes to the data

**New and updated data**

For the first time, peptides from [MassIVE](https://massive.ucsd.edu/ProteoSAFe/static/massive.jsp) (Mass Spectrometry Interactive Virtual Environment) have been included. A total of 736157 peptides from 49 datasets have been integrated in this release. This release also incorporates the latest PeptideAtlas human build v19. This build contains 5 new datasets (cancer cell lines from bone, cancer cell lines from skin, skin cancer, normal skin, and other normal gestational structures), bringing the total to 61 datasets. Taken together, this brings the number of natural peptides (seen by MS) to 2524202, up from 1772990 in the 2019 HUPO reference release.

Data from UniProtKB, IntAct, GOA, GlyConnect and HPA have also been updated. The RNA-seq data is now the merged RNA-seq data set from HPA which consists of HPA, GTEx and FANTOM5 data (previously we integrated only the HPA data). Consequently, the expression levels for the RNA-seq data have changed and are now either detected (corresponding to HPA values NX&ge;1) or not detected (NX<1). This release also includes the new Brain Atlas and Blood Atlas antibody-based data sets from HPA.

**Changes to the PE upgrade rules**

As we now integrate two major mass spectrometry data sets, the following rule is now implemented which ensures that the peptides come from the same data set:

_Entries whose protein(s) existence is based on evidence at the transcript level, homology or a prediction (gene model) are upgraded to evidence at the protein level if the entry has at least 2 unique (or pseudo-unique) peptides **from the same source** of quality GOLD which are 9 or more amino acids in length and which together cover at least 18 aa of the entry isoform._

Following the change in expression levels for the RNA-seq data from HPA, the following rule is now implemented:

_Entries whose protein(s) existence is based on evidence from homology or a prediction (gene model) are upgraded to evidence at the protein level if the entry has an expression profile annotation with evidence assigned by HPA of quality GOLD with RNA-seq evidence (ECO:0000295) and **expression level detected.**_

##Automatic link to the protein digestion tool

The [protein digestion tool](../tools/protein-digestion) implemented in September 2019 allows scientists determine which enzymes and experimental conditions might yield peptides used to identify confidently a protein of interest. In order to facilitate the use of this tool, a &quot;Digest&quot; button has been added that allows the user to seamlessly launch the _in silico_ protein digestion of the displayed isoform. For example, the [Interactions](../entry/NX_P50222/interactions), [Sequence](../entry/NX_P50222/sequence) and [Proteomics](../entry/NX_P50222/proteomics) views for the homeobox protein MOX-2 (NX_P50222) all have this new option.

##Changes to advanced search SPARQL queries

Two new queries have been added:

1. NXQ\_00266 **Proteins binding estradiol and/or similar molecules (substructure search with SMILES) and their associated GO_MF terms**
2. NXQ\_00267 **Proteins binding estradiol and/or similar molecules (similarity search with SMILES), and their associated GO_MF terms**

Both of these queries are only available from the [SNORQL](https://snorql.nextprot.org/) interface.

Six queries have been modified to include MassIVE peptide data: [NXQ\_00075](../proteins/search?mode=advanced&queryId=NXQ_00075), [NXQ\_00077](../proteins/search?mode=advanced&queryId=NXQ_00077), [NXQ\_00226](../proteins/search?mode=advanced&queryId=NXQ_00226), [NXQ\_00227](../proteins/search?mode=advanced&queryId=NXQ_00227), [NXQ\_00228](../proteins/search?mode=advanced&queryId=NXQ_00228) and NXQ\_00229 (SNORQL only). Two queries, [NXQ\_00094](../proteins/search?mode=advanced&queryId=NXQ_00094) and [NXQ\_00222](../proteins/search?mode=advanced&queryId=NXQ_00222), have been modified to take into account the changes in RNA-seq expression levels. 

Finally, warnings have been added to two queries:

1. [NXQ\_00022](../proteins/search?mode=advanced&queryId=NXQ_00022) **Proteins with no function annotated** WARNING This query now excludes PE5 proteins.
2. [NXQ\_00263](../proteins/search?mode=advanced&queryId=NXQ_00263) **Human proteins with baker's yeast orthologs according to OMA** WARNING This  query only works with species with few orthologs.
