The FASTA header for neXtProt entries has the following format:

>db|UniqueIdentifier|GeneName|ProteinName|IsoformName

Where:

* _db_ is 'nxp' for neXtProt.
* _UniqueIdentifier_ is the accession number of the neXtProt isoform. The isoform is specified by '-' followed by an integer number.
* _GeneName_ is the first primary gene name for the neXtProt entry. The ORF name is listed if there is no primary gene name. If there is neither a primary gene name nor an ORF name, '-' is listed.
* _ProteinName_ is the recommended protein name for the neXtProt entry. ??For neXtProt entries without a recommended name, the SubName field is used. In case of multiple SubNames, the first one is used. The 'precursor' attribute is excluded, 'Fragment' is included with the name if applicable.??
* _IsoformName_  is the name of the isoform. 

Examples:

>nxp|NX_P24298-1|GPT|Alanine aminotransferase 1|Iso 1

>nxp|NX_Q6UXH0-1|C19orf80|Angiopoietin-like protein 8|Iso 1

>nxp|NX_P0DMU3-1|-|FAM231A/C-like protein LOC102723383|Iso 1

>nxp|NX_Q13557-10|CAMK2D|Calcium/calmodulin-dependent protein kinase type II subunit delta|Delta 10
