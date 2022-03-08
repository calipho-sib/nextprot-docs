This release, neXtProt data release 2022-02-25, is the 2022 reference for the [HUPO](https://www.hupo.org/) C-HPP project.

##Changes to the data

**Peptide data**

This release incorporates the latest [PeptideAtlas](http://www.peptideatlas.org) human 2022-01 build. This build contains 2 new sample types (normal muscle, cancer from other female reproductive organ), bringing the total number of PeptideAtlas sample types to 64. Peptides from [MassIVE](https://massive.ucsd.edu/) have also been updated. MassIVE peptides from 7 new tissue types (normal oocyte, brain cancer, kidney cancer, liver cancer, urinary bladder cancer, cancer cell lines from colon, as well as cancer cell lines from other gestational structure) have been integrated in this release. Taken together, this brings the number of natural peptides seen by mass Spectrometry (MS) to 3280422, up from 2726064 in the 2021 HUPO reference release.

**Updated data**

UniProt release 2021_04, Ensembl release 104 and HPA version 21 have also been integrated. Data from the Cellosaurus, GOA, GlyConnect and neXtProt has also been updated.

**Modified data**

The GOLD/SILVER quality rule applying to the binary-interaction data from ENYO Pharma SA has been modified to be coherent with that applied to data from IntAct.

##Changes to the user interface

The antibody track has been removed from the Peptides view as it focusses on the peptides detected by MS. Antibodies are still displayed in the Proteomics view. Example: Antibody HPA039242 from the Human Protein Atlas (HPA) to barrier-to-autointegration factor (BANF1) [NX\_O75531](../entry/NX_O75531/proteomics)

##New advanced search SPARQL queries

The following query of interest to the rare disease community has been added:

* NXQ\_00294 **Variants in MECP2 causing Rett Syndrome**

to the [SNORQL](https://snorql.nextprot.org/) interface.

##New predictions of protein functions

Function predictions for 1 additional entry ([NX\_P0C7W6](../entry/NX_P0C7W6/function-predictions)) are now available. This brings the total number of entries with function predictions to 29 entries. Entries with function predictions are listed in the [functional proteome project](../about/functional-proteome-project) page. 
