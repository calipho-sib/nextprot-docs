New function predictions 

Function predictions, compiled from 65 articles and bioinformatics tools, were added for 39 proteins. This brings the total number of entries with predictions to 239, out of the 1,521 entries https://www.nextprot.org/proteins/search?mode=advanced&queryId=NXQ_00022  that have no function annotated in the current release. The list of entries with predictions is found here https://www.nextprot.org/proteins/search?listId=3O1KQY7L.
Help us reach the 500 entry mark! We're calling on all annotators and bioinformaticians to submit predictions or additional evidence supporting the predictions. We're also eager to have web lab scientists test the predictions experimentally and publish the results to help us advance our knowledge of the human proteome.

Changes to the RDF model

:BindingSite instances now have an :interactant property.
This property links every binding site to an :Xref instance pointing to a ChEBI chemical compound identifier.
These changes are implemented in the schema file which can be downloaded from https://download.nextprot.org/pub/current_release/rdf/ttl/schema.ttl.gz.
The documentation has been updated at http://nextprot.org/rdf.

Changes to the SPARQL queries

Updated queries

The following query used to give wrong results and has been corrected 
•	NXQ_00143 Proteins for which none of the reported proteotypic peptides is from PeptideAtlas nor MassIVE

the following query has been refactored to reflect the changes in the representation of metal binding sites (see above)
•	NXQ_00290 Proteins that are enzymes requiring the cofactor Ca(2+) and with a calcium binding site

Queries removed

Due to the increase in the number of peptides in neXtProt the following queries do not work anymore (time out) and have been removed
•	NXQ_00227 Proteins with at least 2 peptides >=9aa found in testis, but with no peptide identified in sperm [lost during sperm maturation]
•	NXQ_00228 Proteins with at least 2 validating peptides >=9aa AND which are not overlapping found in blood plasma, urine or cerebrospinal fluid (criteria for biomarker).
•	NXQ_00229 Proteins with 2 peptides from only one PeptideAtlas/MassIVE data set

