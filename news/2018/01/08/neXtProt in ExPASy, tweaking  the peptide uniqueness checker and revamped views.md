##Query neXtProt via ExPASy

[ExPASy](https://www.expasy.org/), the SIB Bioinformatics Resource Portal which provides access to scientific databases and software tools (i.e., resources) in different areas of life sciences, now includes neXtProt in its cross-resource query system.

##Changes to the tools

The [Peptide uniqueness checker](../tools/peptide-uniqueness-checker) has been adapted to take into account entries with identical isoform sequences. Previously peptides matching such sequences were considered to be “Found in other entries”; such peptides are now considered to be “Pseudo-unique” and entries or isoforms having identical sequences are labelled with an asterisk.

##Revamped Identifiers view for entries

Identifiers uniquely identify an entry. The Protein Identifiers and Gene Identifiers views overlapped considerably and have hence been merged for ease of use. Searching for Affymetrix or Illumina microarray probe identifiers returns the corresponding entry. For example, searching for the Affymetrix microarray probe [202911_at](https://www.nextprot.org/proteins/search?query=202911_at) retrieves DNA mismatch repair protein Msh6 (MSH6).
