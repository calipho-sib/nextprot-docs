With this latest release all entry views have been updated and now load more quickly.

##Revamped Exon view for entries

The Exon view provides information concerning the gene(s) and the exons coding for the isoforms included in the entry. The "Gene information" section lists the name, chromosomal location, orientation, length and Ensembl identifier of each gene. Special cases where the gene maps to multiple Ensembl genes (for instance [HIST1H4A](https://www.nextprot.org/entry/NX_P62805/exons)), does not map to the current genome assembly (i.e. [DUX5](https://www.nextprot.org/entry/NX_Q96PT3/exons)) or when an isoform cannot be aligned to the gene (i.e. [ERVK-7](https://www.nextprot.org/entry/NX_P61567/exons)) are indicated. The "Exon" section displays which exon is found in which transcript and which amino acid it encodes, with the reading frame indicated. The canonical isoform, as defined by UniProtKB, is now labelled for improved clarity.

##Export in FASTA format

In response to a user request, an API method to retrieve all the isoforms in the current release as FASTA has been implemented at [https://api.nextprot.org/export/entries/all.fasta] 

##Peptide uniqueness checker fix

The Peptide uniqueness checker in our user [interface](../tools/peptide-uniqueness-checker) and [API](https://api.nextprot.org/) returned no results for peptides matching a sequence with a known variant (the pepx program handled this correctly). Checking peptide EDAIWRLLF found in Isoform 1 of Transmembrane protein 87A (NX_Q8NBN3) with the D -> E variant at position 441 now returns this entry.  
