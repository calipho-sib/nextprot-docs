We're very excited to present our improved version of the simple search tool, and a new SPARQL-based advanced search, as described in our [2015 Nucleic Acids Research database](http://dx.doi.org/10.1093/nar/gku1178) update.

You can access the tools at [search.nextprot.org](http://search.nextprot.org/). We encourage all users to explore our new search tools, especially the advanced search capabilities and to try out some of the example queries that we provide. We also invite you to create an account to access additional functionality, including creating, saving and managing lists resulting from queries.

In terms of data, our new release has a strong focus on proteomics, with new data and improved rules:

* [Human 2015-03](https://db.systemsbiology.net/sbeams/cgi/PeptideAtlas/buildDetails?atlas_build_id=442) build of PeptideAtlas has been integrated.
* Peptides and sumoylation sites from [Hendricks et al.](http://dx.doi.org/10.1038/nsmb.2890) have been incorporated.
* Except for SRM peptides, all peptides less than 7 aa in length have been removed.
* For natural peptides, we now represent the ambiguous amino-acids isoleucine and leucine as "J", and ignore them for the determination of proteotypicity of peptides.
* The rules for assigning "existence at protein level" using mass spectrometry data have been improved to take into account the length and number of peptides: at least 2 peptides 7 or 8 aa in length or 1 peptide 9 aa in length of more are now necessary to trigger this assignment.

**FTP site**
* The chromosome report files in TXT format have been fixed so that the data is aligned. Following the change in Swiss-Prot ACs, these were no longer aligned due to the presence of 13-digit neXtProt ACs.
* Proteins which are encoded by multiple genes mapping to different chromosomes are now integrated in all the relevant PEFF and XML chromosome files.
