September 2016 neXtProt release


*Changes to the data*

We are particularly pleased to announce that new variant phenotype data annotated by the neXtProt team has been integrated. New sequence variations arising either from mutagenesis or variants found in patients have been added, as well as their effect on the molecular function, biological process, cellular localization, interaction with another protein or small molecule or mammalian phenotype. The data for the following entries is presented in the new portals:
# Breast cancer: BRCA1, BRCA2, EPCAM, MLH1, MLH3, MSH2, MSH6, PMS2 
# Sodium channels: SCN1A, SCN2A, SCN3A, SCN4A, SCN5A, SCN8A, SCN9A, SCN10A, SCN11A
This data is presented in the new Phenotype view, as well as the Structures view.  ??? However, for operational reasons, the new variants are not yet displayed in the Sequence view, included in our PEFF files or in the API.

This release of neXtProt also includes an update to Ensembl Release 84, as well as updates of UniProtKB, IntAct and GO annotations. Compared to our previous release, over 2,500,000 additional variants have been incorporated. 

*Changes to the tools*

A new tool for the proteomics commnunity, the peptide unicity checker, is now available. Up to 1000 peptides from mass spectrometry experiments can be analyzed in one go to determine their proteotypicity. The analysis can deal with single aa substitutions or deletions. It does not handle multiple aa substitutions or deletions, as well as insertions (single or multiple). To our knowledge, this is the first program to implement the possibility to take into account variants or not, thus leveraging the large number of variants integrated in neXtProt.

Furthermore a new version of BioViz is now used to view 3D protein structures in the Structures view. This new version more user-friendly than the previous version.

Finally a newer version of blast, version 2.3.0, has been installed. Blasting a sequence consisting of the same amino acid now return results. 

*Changes to the access to neXtProt*
Following a transition period in which we provided two web sites to access neXtProt data, the original www.nextprot.org and the new search.nextprot.org website with an improved simple and advanced (RDF) search, all the data and functionalities are available from a single web site again. We have taken this opportunity to freshen up our user interface while maintaining the look and feel of our original web site. We hope you will take this opportunity to explore the universe of human proteins on neXtProt and let us know what you think. 

*Changes to the XML*
A new version of our XSD, version 2, is on the FTP site. Changes are documented in a comment at the beginning of the XSD file.

*Changes to the files available by FTP*
# A number of new controlled vocabularies used in the new variant phenotype data have been included: {{}} 
# As the Cellosaurus files are available from Expasy site [ftp://ftp.expasy.org/databases/cellosaurus/], they have been removed from the neXtProt FTP site.
# Unfortunately, as of September 2016, the old XML format can no longer be provided due to technical constraints. Specifically, our API had to be modified to incorporate the new variant phenotype data.
