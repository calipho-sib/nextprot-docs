##Changes to the data

**Updated proteomics data**

This latest release, neXtProt data release 2019-01-11, is the 2019 reference for the [HUPO](https://www.hupo.org/) C-HPP project. It incorporates the latest PeptideAtlas human build. This build contains 4 additional datasets (olfactory system, pancreatic cancer, pancreatic cancer cell lines and cancer of other female reproductory organs), bringing the total  number of PeptideAtlas datasets to 56. The latest human SRMAtlas data has also been loaded.

**Additional data updated**

UniProt release 2018\_11, with its introduction of [Rhea](https://www.rhea-db.org/) as a vocabulary to annotate and represent enzyme-catalyzed reactions, has also been integrated. Rhea is a manually curated knowledgebase of biochemical reactions that uses the [ChEBI](https://www.ebi.ac.uk/chebi/) (Chemical Entities of Biological Interest) ontology to describe reaction participants, their chemical structures, and chemical transformations. This information has allowed us to generate small-molecule-interaction annotations, displayed in the Interactions view, describing the interaction between proteins and chemicals. Example: [NX\_Q92781](../entry/NX_Q92781/interactions)

Data from IntAct, GOA and GlyConnect have also been updated.

##Changes to the export files

**Changes to the PEFF export files**

The following PEFF format changes have been implemented:

1.	For all isoforms \DbUniqueId=nnn has been removed 
2.	For disulfide bonds \ModRes=(2||Disulfide) has been replaced with \ModResPsi=(2|MOD:00798|half cystine)
3.	The terms PEFF:0001020 (mature protein), PEFF:0001021 (signal peptide), PEFF:0001022 (transit peptide) and PEFF:0001034 (propeptide) have been introduced

The following examples illustrate the changes:

1.	Changes 1, 2 and 3 (signal peptide, propeptide and mature protein): [NX\_P01308](https://api.nextprot.org/export/entry/NX\_P01308.peff)
2.	Changes 1 and 3 (transit peptide, mature protein):  [NX\_Q5U4N7](https://api.nextprot.org/export/entry/NX\_Q5U4N7.peff)

**Changes to the XML**

Our XSD file available at [ftp://ftp.nextprot.org/pub/current\_release/xml/nextprot-export-v2.xsd](ftp://ftp.nextprot.org/pub/current_release/xml/nextprot-export-v2.xsd) has been updated to take into account the changes in the catalytic-activity annotations. The changes are documented in a comment at the beginning of the XSD file.

##Changes to the API

**New protein digestion tool**

A new tool that performs _in silico_ protein digestion is now available via our [API](https://api.nextprot.org/). The tool allows the user to input the neXtProt accession for a specific isoform or entry and returns the peptide sequences obtained upon digestion. Additional information is provided in the [Help > Tools](../help/tools) page.

The protein digestion tool can be combined with the peptide uniquenesss checker to determine which proteases, other than trypsin, can be used to identify trypsin-resistant proteins by mass spectrometry. For example, trypsin digestion of the cancer-testis antigen CTAGE1 (NX\_Q9HC47) does not yield a peptide of 9-35 aa; however digestion with Glu-C endopeptidase in phosphate buffer (GLU\_C\_PHOSPHATE) results in a proteotypic peptide of 32 aa.

Comments and suggestions for improvements to this tool are welcome!

##New kinase portal

Function data for 308 human protein kinases annotated by the neXtProt team is now available in the [Protein kinase function portal](../portals/kinase-function). A total of 22,341 entries, including 5,851 phosphorylations, captured from 9,081 publications can now be explored and downloaded.

##Advanced search SPARQL queries

The following example query has been added:

1. [NXQ\_00246](../proteins/search?mode=advanced&queryId=NXQ_00246) **Proteins which are enzymes catalyzing a reaction involving lipids**

