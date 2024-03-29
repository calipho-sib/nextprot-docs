This release, neXtProt data release 2023-04-18, is the 2023 reference for the [HUPO](https://www.hupo.org/) C-HPP project.. 

## Changes to the data
**Peptide data**

This release incorporates the latest [PeptideAtlas](https://peptideatlas.org/) human 2023-01 build. Peptides from [MassIVE](https://massive.ucsd.edu/) have also been updated. Taken together, this brings the number of natural peptides seen by mass spectrometry (MS) to 3754276, up from 3280422 in the 2022 HUPO reference release.

Entries for which at least 2 non overlapping proteotypic peptides of 9 aminoacids or more have been reported in a single data source (PeptideAtlas or MassIVE) now have the keyword [KW-1267 Proteomics identification](https://www.nextprot.org/term/KW-1267/).
 
**Updated data**

UniProt release 2022_05 and Ensembl release 107 have also been integrated. Data from the Cellosaurus, GOA, GlyConnect, IntAct and neXtProt has also been updated.

## Changes to the user interface

We changed our definition of disease-associated proteins, which is used to compute the *Disease yes/no* value in protein search results. 
The *Disease* value is now set as *yes* for proteins with either a disease annotation OR a UniProt keyword of the disease category, except KW-0656 "Proto-oncogene".

For more transparency, the [Release statistics page](https://www.nextprot.org/about/statistics) now includes links to SPARQL queries to show our users how the numbers were computed. The missing queries will be added in the upcoming releases.

## Changes to the SPARQL queries

**New queries**

These two queries make use of the new keyword KW-1267 to retrieve all entries whose protein existence is confirmed by mass spectrometry (according to the HUPO HPP guidelines), and conversely all the ones that whose protein existence was validated using other criteria than mass spectrometry:

* NXQ\_00301 **PE1 entries that comply with HPP guidelines (at least 2 non overlapping peptides of at least 9aa from a single data source)**
*	NXQ\_00302 **PE1 entries that do not comply with HPP guidelines (at least 2 non overlapping peptides of at least 9aa from a single data source)**

**Updated queries**

The six queries that retrieve disease-associated proteins have been refactored to take the new definition into account (see above)

*	NXQ\_00006 **Proteins whose genes are on chromosome 13 and are associated with a disease**
*	NXQ\_00025 **Proteins with at least 50 interactors that are not associated with a disease**
*	NXQ\_00028 **Proteins associated with a disease but without a disease-causing amino-acid substitution variant**
*	NXQ\_00081 **Proteins with at least one 3D structure and that are located in the mitochondrion and are linked with a disease**
*	NXQ\_00090 **Proteins which are linked to a disease and that do not have orthologs/paralogs in mouse**
*	NXQ\_00208 **Proteins which are ion channels and are associated with a disease**

**Query removed**

Due to a change in the representation of metal binding sites, the following query does not work anymore and has been removed. 

*	NXQ\_00290 **Proteins that are enzymes requiring the cofactor Ca(2+) and with a calcium binding site**

