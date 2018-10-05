##Changes to the data

**New and updated data**

neXtProt data release 2018-09-03 incorporates and links to [Human Protein Atlas](https://www.proteinatlas.org/) (release 18). The evidence code for the immunohistochemistry (IHC) data from Human Protein Atlas (HPA) has been changed from ECO:0000087 immunolocalization evidence to ECO:0001055 immunohistochemistry evidence. 

Data from UniProtKB, Ensembl, IntAct, COSMIC and GOA have also been updated and two new data sets integrated:

1. **Glycosylation sites** from [GlyConnect](https://glyconnect.expasy.org/).
2. **Phosphorylation and interaction data** annotated by neXtProt for most of the human protein kinases.

**Antibody mapping**

neXtProt now provides information as to whether an antibody mapping is "unique", "pseudo-unique" or "not unique" in a manner analogous to that of peptide mappings. Antibodies mapping to multiple entries sharing an identical sequence (pseudo-unique) can thus now be distinguished from those mapping to multiple entries with differing sequences (not unique). Please note that the criteria for mapping peptides differs from those for mapping antibody epitopes &#8208; while peptides must align with an exact 100% match to the isoform sequence, antibodies must align (Smith&#8208;Waterman algorithm) with a score of 80 or more with some gaps allowed.

**New rule to upgrade protein existence**

As we now integrate curated phosphorylation data, the following rule has been implemented so as to be consistent with the rules applied at UniProtKB: 

> Entries whose protein(s) existence is based on evidence at the transcript level, homology or a prediction (gene model) are upgraded to evidence at the protein level if the entry has GOLD modified residue annotations with experimental evidence other than mass spectrometry from a source other than UniProtKB.

##Advanced search SPARQL queries

The following query has been added:

1. [NXQ\_00244](../proteins/search?mode=advanced&queryId=NXQ_00244) **Proteins with a variant having an impact on a binary interaction**

The following queries have been modified to take into account the change in evidence code for the immunohistochemistry data from HPA:

1. [NXQ\_00020](../proteins/search?mode=advanced&queryId=NXQ_00020) **Proteins with at least 2 HPA antibodies whose genes are located on chromosome 21 and that are highly expressed at IHC level in heart**
2. [NXQ\_00077](../proteins/search?mode=advanced&queryId=NXQ_00077) **Proteins which are expressed in liver according to IHC data but not found in HUPO liver proteome set**
3. [NXQ\_00221](../proteins/search?mode=advanced&queryId=NXQ_00221) **Proteins with RNA-seq expression level "not detected" and IHC expression level: "high" (same tissue or children)**
4. [NXQ\_00222](../proteins/search?mode=advanced&queryId=NXQ_00222) **Proteins with RNA-seq expression level "high" and IHC expression level "high" in brain or one of its subparts**
5. [NXQ\_00235](../proteins/search?mode=advanced&queryId=NXQ_00235) **Proteins with at least two antibodies available from Human Protein Atlas that have associated tissue expression annotations from immunohistochemistry studies**
