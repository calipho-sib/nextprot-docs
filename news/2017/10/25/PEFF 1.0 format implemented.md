The PSI Extended FASTA Format ([PEFF](http://www.psidev.info/peff)) allows the representation of annotations such as post-translational modifications, mutations and other processing events across sequence databases to be unified, thereby improving their usability by sequence search engines and other associated tools. The Proteomics Standards Initiative (PSI) of the Human Proteome Organization (HUPO) has just finished defining the PEFF 1.0 format which is implemented in this release. 

"NumberOfEntries" now corresponds to the number of sequence entries in the PEFF file and not the number of neXtProt entries as was previously the case. PEFF files including all isoform sequences for both individual and multiple entries can be downloaded from the search results page (for example, [search in proteins for MSH6](https://api.nextprot.org/export/entries.peff?query=MSH6)), when viewing lists or running private queries. Files for individual entries can also be downloaded from any entry view. Files with all the entries for a chromosome or in a release are available from our FTP site at [ftp://ftp.nextprot.org/pub/current\_release/peff/](ftp://ftp.nextprot.org/pub/current_release/peff/).