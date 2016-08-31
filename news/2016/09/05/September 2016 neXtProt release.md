**Changes to the data**

We are pleased to announce that new variant phenotype data annotated by the neXtProt team has been integrated. New sequence variations arising either from mutagenesis or variants found in patients have been added, as well as their effect on the molecular function, biological process, cellular localization, interactions or mammalian phenotype. The data for the following entries is presented in the new portals:

1. **[Cancer Variant Portal](http://www.nextprot.org/portals/breast-cancer)**: BRCA1 
2. **[NavMut Portal](http://www.nextprot.org/portals/navmut)** on sodium channels: SCN1A, SCN2A, SCN3A, SCN4A, SCN5A, SCN8A, SCN9A, SCN10A, SCN11A

This data is presented in the new Phenotype view, i.e. for the [DNA mismatch repair protein Msh6](http://alpha-search.nextprot.org/entry/NX_P52701/phenotypes), as well as the Structures view, and in the newest version of our [API](https://api.nextprot.org/). Note that the data is not included in the release statistics (Variants only), search results, Sequence view for entries, or PEFF files.

This release of neXtProt also includes an update to Ensembl Release 84, as well as updates of UniProtKB, IntAct and GO annotations. Compared to our previous release, over 2,500,000 new variants have been incorporated. 

**Changes to the tools**

A new tool for the proteomics commnunity, the **[Peptide Unicity Checker](http://www.nextprot.org/tools/unicity-checker)**, is now available. Up to 1,000 peptides from mass spectrometry experiments can be analyzed in one go to determine their proteotypicity with respect to either neXtProt entries or isoforms. The analysis can deal with single (but not multiple) amino acid substitutions or deletions. It cannot handle insertions (single or multiple). To our knowledge, this is the first program to implement the possibility to take into account variants, thus leveraging the large number of variants integrated in neXtProt.

Furthermore a new version of our 3D structure viewer, **BioViz**, developed by BIONEXT, is now in the Structures view. Try it out on [insulin](http://nextprot.org/entry/NX_P01308/structures) or your favorite protein!

Finally a newer version of **blast** (2.3.0) has been installed. 

**Revamped neXtProt home page**

We have taken this opportunity to freshen up our user interface while maintaining the look and feel of our original web site. We hope you will take this opportunity to explore the universe of human proteins on neXtProt and let us know what you think. 

**Changes to the XML**

A new version of our XSD, version 2, is on the FTP site. Changes are documented in a comment at the beginning of the XSD file. Unfortunately, as of September 2016, the old XML format can no longer be provided due to technical constraints.

**Changes to the files available by FTP**

1. Two new controlled vocabularies used in the variant phenotype data have been included: {{}} 
2. The Cellosaurus files have been moved to the Expasy site [ftp://ftp.expasy.org/databases/cellosaurus/] and removed from the neXtProt FTP site.
