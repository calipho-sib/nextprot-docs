##Analyze

The data in neXtProt can be analyzed using the following tools:

**BLAST** 

neXtProt provides access to a simple BLAST implementation in the Medical, Interactions, Localization, Sequence, Proteomics and Structures entry views. To find other entries in neXtProt containing the same or a similar sequence, you can:

* BLAST the entire sequence by clicking on the "BLAST sequence" button
* Select part of the sequence (shown highlighted) and click on the "BLAST selection" button 

**[List management](/help/protein-lists)**

A list is a collection of protein entries that you have created. neXtProt allows you to create and manage private lists.

**Peptide uniqueness checker**

The "uniqueness checker" was designed to help scientists determine which peptides are unambiguous and can thus be used to confidently identify protein entries. Up to 999 peptides can be analyzed with this tool.

It uses the [pepx program](https://github.com/calipho-sib/pepx) which is based on a 6-mer amino-acid index regenerated at each neXtProt release. The 6 aa length was chosen as it significantly speeds up the mapping process.

A peptide is considered as matching an isoform/entry sequence when all 6-mers covering the peptide return the same sequence. Leucine and isoleucine are always considered equivalent.

To compute "additional mappings with known variants", pepx takes into account the vast number of SNPs and disease mutations described in neXtProt.  At present, pepx considers one single amino acid substitution or deletion per 6-mer; substitutions and deletions more than 1 aa in length, as well as insertions, are not taken into account. Consequently pepx returns a match if single amino acid variations in the isoform sequence are spaced at least 5 amino acids from each other.

The "uniqueness checker" categorizes peptides into "Unique", "Pseudo-unique" and "Not unique" (previously referred to as "Found in other entries") depending on the match results. "Unique" peptides map to only 1 entry. Peptides mapping to multiple entries which can be considered to be the same due to sequence identity are "Pseudo-unique", with entries or isoforms with identical sequences displayed with an asterisk. "Unique" and "Pseudo-unique" peptides are considered to unambiguously identify proteins. Peptides which are "Not unique" match multiple entries which differ in sequence.

**Protein digestion**

An _in silico_ protein digestion tool is available in the Tools section of our [API](https://api.nextprot.org/). The tool determines the peptides obtained upon digestion of a specific isoform or entry with the specified protease. In combination with the peptide uniquenesss checker, this tool can help determine which proteases, other than trypsin, can be used to identify trypsin-resistant proteins by mass spectrometry.

_Cleavage specificities of selected enzymes and chemicals:_

In the substrate being cleaved, amino acid residues are designated P1, P2, P3, P4 etc. in the N-terminal direction from the cleaved bond whereas the residues in C-terminal direction are designated P1', P2', P3', P4'. etc.

Protease | P4 | P3 | P2 | P1 | P1' | P2' 
---------|----|----|----|----|-----|-----
**ARG_C** (Arg-C proteinase) | 
**ASP_N** (Asp-N endopeptidase) | 
**BNPS_SKATOLE** (BNPS-Skatole) | 
**CASPASE_1** (Caspase 1) | 
**CASPASE_2** (Caspase 2) |	
**CASPASE_3** (Caspase 3) |	
**CASPASE_4** (Caspase 4) |	
**CASPASE_5** (Caspase 5) | 
**CASPASE_6** (Caspase 6) |	
**CASPASE_7** (Caspase 7) |	
**CASPASE_8** (Caspase 8) | 
**CASPASE_9** (Caspase 9) |	
**CASPASE_10** (Caspase 10)	|
**CHYMOTRYPSIN_FYL** (Chymotrypsin) |
**CHYMOTRYPSIN_FYLW** (Chymotrypsin) |
**CHYMOTRYPSIN_HIGH_SPEC** (Chymotrypsin-high specificity) |
**CHYMOTRYPSIN_LOW_SPEC** (Chymotrypsin-low specificity) |
**CNBR** (CNBr) |
**ENTEROKINASE** (Enterokinase) |
**GLU_C_BICARBONATE** (Glu-C endopeptidase in ammonium bicarbonate or acetate) |
**GLU_C_PHOSPHATE** (Glu-C endopeptidase in phosphate buffers) |
**LYS_C** (LysC) |
**PEPSIN_PH_1_3** (Pepsin pH1.3) |
**PEPSIN_PH_GT_2** (Pepsin pH>2) |
**PROTEINASE_K** (Proteinase K) |
**THERMOLYSIN** (Thermolysin) |
**TRYPSIN** (Trypsin) |

For additional information, please refer to the [PeptideCutter](https://web.expasy.org/peptide_cutter/peptidecutter_enzymes.html) documentation.
