##Analyze

The data in neXtProt can be analyzed using the following tools:

**BLAST** 

neXtProt provides access to a simple BLAST implementation. To find other entries in neXtProt containing the same or a similar sequence, you can:

* BLAST the entire sequence by clicking on the "BLAST sequence" button
* Select part of the sequence (shown highlighted) and click on the "BLAST selection" button 

**[List management](/help/protein-lists)**

A list is a collection of protein entries that you have created. neXtProt allows you to create and manage private lists.

**Peptide Unicity Checker**

The "unicity checker" was designed to help scientists determine which peptides are unambiguous and can thus be used to confidently identify protein entries. Up to 999 peptides can be analyzed with this tool.

It uses the [pepx program](https://github.com/calipho-sib/pepx) which is based on a 6-mer amino-acid index regenerated at each neXtProt release. The 6 aa length was chosen as it significantly speeds up the mapping process.

A peptide is considered as matching an isoform/entry sequence when all 6-mers covering the peptide return the same sequence. Leucine and isoleucine are always considered equivalent.

To compute "additional mappings with known variants", pepx takes into account the vast number of SNPs and disease mutations described in neXtProt.  At present, pepx considers one single amino acid substitution or deletion per 6-mer; substitutions and deletions more than 1 aa in length, as well as insertions, are not taken into account. Consequently pepx returns a match if single amino acid variations in the isoform sequence are spaced at least 5 amino acids from each other.
