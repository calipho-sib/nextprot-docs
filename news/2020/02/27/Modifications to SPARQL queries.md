One new query has been added:

1. NXQ\_00270 **Proteins belonging to Rett syndrome pathways, and their subcellular  locations (GOLD)** This is a federated query with WikiPathways displayed only in the [SnorQL](https://snorql.nextprot.org/) interface.

The following queries have been modified:

1. [NXQ\_00058](../proteins/search?mode=advanced&queryId=NXQ_00058) **Proteins which are located on the genome next to a protein which is involved in spermatogenesis** This query has been rewritten and now returns results more quickly.
2. [NXQ\_00099](../proteins/search?mode=advanced&queryId=NXQ_00099) **Secreted proteins that have at least one PTM in a position of a variant** This query now returns results more quickly as only positions on the SwissProt displayed isoform are considered. Note that proteins whose location is &quot;extracellular exosome&quot;-only are now excluded.
3. [NXQ\_00105](../proteins/search?mode=advanced&queryId=NXQ_00105) **Proteins with at least one cross-reference to SMR (Swiss Model Repository) but no cross-references to PDB** As cross-references to ProteinModelPortal were deleted in our last data release, the query gave an error. It has been replaced by the current query, **Proteins with at least one cross-reference to SMR (Swiss Model Repository) but no cross-references to PDB**, which returns results.
4. [NXQ\_00139](../proteins/search?mode=advanced&queryId=NXQ_00139) **Protein kinases which are high-confidence drug targets according to CHEMBL** This query, which used to return an error, now returns results.
5. NXQ\_00266 **Proteins binding estradiol and/or similar molecules (substructure search with SMILES) and their associated GO_MF terms** This query, which used to return an error, now returns results in the [SnorQL](https://snorql.nextprot.org/) interface.
6. NXQ\_00267 **Proteins binding estradiol and/or similar molecules (similarity search with SMILES), and their associated GO_MF terms** This query, which used to return an error, now returns results in the [SnorQL](https://snorql.nextprot.org/) interface.
