This first release of the year focuses on proteomics. Specifically, the following new data has been integrated in neXtProt:

* The new PeptideAtlas Human 2016-01 build has been integrated. Phosphorylation data that was previously loaded from individual studies (PMIDs 19413330, 20068231, 21406692, 22199227, 22468782, 23312004) is now loaded through the global PeptideAtlas Human 2016-01 (peptides) and PeptideAtlas phosphoproteome (PTM sites). This avoids FDR pile-up. Please note that we only integrated phosphorylation sites with a PTM score >0.95 (those with a PTM score >0.99 are labeled as gold).
* For the first time ADP-ribosylation sites have been integrated. ADP-ribosylation sites and the corresponding peptides from [Zhang et al.](http://dx.doi.org/10.1038/nmeth.2603) have been incorporated.  
* Acetylation sites with their corresponding peptides from [Sun et al.](http://linkinghub.elsevier.com/retrieve/pii/S1874-3919(14)00347-9) have also been loaded.

This latest release of neXtProt also includes an update to Ensembl Release 82, as well as updates of UniProtKB, IntAct and GO annotations.

The following rules have been modified:

* Entries whose protein(s) existence is based on evidence at the transcript level, homology or a prediction (gene model) were previously upgraded to evidence at the protein level if the entry had (i) 2 peptides 7 or 8 amino acids in length or (ii) 1 peptide at least 9 aa coming from mass spectrometry experiments in neXtProt. This rule has been made more stringent so as to be in synch with the HPP criteria for validating proteins using mass spectrometry data. At least 2 peptides 9 aa in length or more which differ in at least 1 amino acid and which are not overlapping are now required for the protein evidence to be upgraded.
* An N-acetylation can now be located on the N terminal residue of a propeptide as propeptides are not always cleaved and the protein often exists in the mature form with the propeptide. This was previously not allowed.

The FTP site now includes:

* The controlled vocabulary file cv_carbohydrate.txt
* The new cellosaurus_faq.txt file
* Files listing the PE1 entries with the current and previous criteria
* Some of the RDF ttl files have been renamed. All chromosome files now start with "nextprot_chromosome_", whereas all expression files start with "expression_".
