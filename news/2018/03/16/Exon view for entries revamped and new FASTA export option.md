With this latest release all entry views have been updated and now load more quickly.

##Revamped Exon view for entries

The Exon view provides information concerning the gene encoding the entry and the exons coding for the different isoforms. The "Gene information" section lists the chromosomal location of the gene, its orientation, its position on the chromosome, its length and the Ensembl gene to which it corresponds. The position of the coding region on the genome is also provided. Special cases where the gene coding for an entry maps to multiple Ensembl gene (for instance [HIST1H4A](https://www.nextprot.org/entry/NX_P62805/exons)), does not map to the current genome assembly (i.e. [DUX5](https://www.nextprot.org/entry/NX_Q96PT3/exons)) or when an isoform cannot be aligned to the gene (i.e. [ERVK-7](https://www.nextprot.org/entry/NX_P61567/exons)) are indicated. The "Exon" section displays what exon is found in which transcript and which amino acid it encodes, with the reading frame indicated.

It is now possible to search in "Exon" section for a specific Ensembl exon or transcript ID. For instance, searching for "ENST" returns the number of Ensembl transcripts which can be mapped for the entry.

##Export in FASTA format

In response to a user request, an API method to retrieve all the isoforms in the current release as FASTA has been implemented at [https://api.nextprot.org/export/entries/all.fasta]
