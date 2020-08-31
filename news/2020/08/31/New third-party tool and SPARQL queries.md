##Changes to tools

The neXtProt platform hosts third-party tools to provide useful functionalities for our users. These are available from the &quot;Community&quot; section in the left menu of the entry pages.

**If you have developed a tool applicable to human proteins and would like to provide it via the neXtProt platform, please contact us!**

**New community tool**

For each neXtProt entry, we now provide information from SAAVpedia, a resource developed by the Chromosome 11 team of C-HPP (PI: Jong Shin Yoo at the Korea Basic Science Institute). Example: APOE [NX\_P02649](https://www.nextprot.org/entry/NX_P02649/gh/sweetrain096/SAAVpedia)

[SAAVpedia](https://www.saavpedia.org/) is a comprehensive interpretation platform that allows users to identify, annotate, and retrieve single amino acid variants (SAAVs) from proteomic and genomic sequence data. SAAVpedia provides a proteogenomic analysis pipeline to prioritize and interpret SAAVs ([Hwang _et al,_ 2019](https://doi.org/10.1021/acs.jproteome.9b00366)).

This new tool provides valuable additional information including the position and variation at the genomic level, the phenotypic effect of the variant described using the **Experimental Factor Ontology** (EFO) and the **Human Phenotype Ontology** (HPO), as well as providing ClinVar identifiers for the SAAVs.

##Changes to SPARQL queries

The following queries exploring the PPI data in neXtProt have been added in the [SnorQL](https://snorql.nextprot.org/) interface:

1. NXQ\_00281 **Protein pairs with at least 50 common interactors (excluding keratins)**
2. NXQ\_00282 **Proteins with an interaction mapping encompassing a coiled coil or bZip region**
3. NXQ\_00283 **Proteins with no reported mitochondrial localization but interacting with 20 or more mitochondrial proteins ('gold' quality)**
4. NXQ\_00286 **Protein domains or regions that frequently occur in interaction mappings**
