This release, neXtProt data release 2022-02-25, is the 2022 reference for the [HUPO](https://www.hupo.org/) C-HPP project. One entry on chromosome 10 with protein existence evidence at protein level (PE1), [O75112](https://www.uniprot.org/uniprot/O75112), is missing. This issue will be fixed in our next data release.

##Changes to the data

**Peptide data**

This release incorporates the latest [PeptideAtlas](http://www.peptideatlas.org) human 2022-01 build. This build contains 2 new sample types (normal muscle, cancer from other female reproductive organ), bringing the total number of PeptideAtlas sample types to 64. Peptides from [MassIVE](https://massive.ucsd.edu/) have also been updated. MassIVE peptides from 7 new tissue types (normal oocyte, brain cancer, kidney cancer, liver cancer, urinary bladder cancer, cancer cell lines from colon, as well as cancer cell lines from other gestational structure) have been integrated in this release. Taken together, this brings the number of natural peptides seen by mass Spectrometry (MS) to 3280422, up from 2726064 in the 2021 HUPO reference release.

**Updated data**

UniProt release 2021_04, Ensembl release 104 and HPA version 21 have also been integrated. Data from the Cellosaurus, GOA, GlyConnect and neXtProt has also been updated.

**Modified data**

The GOLD/SILVER quality rule applying to the binary-interaction data from ENYO Pharma SA has been modified to be coherent with that applied to data from IntAct.

##Changes to the user interface

The antibody track has been removed from the Peptides view as it focusses on the peptides detected by MS. Antibodies are still displayed in the Proteomics view. Example: Antibody HPA039242 from the Human Protein Atlas (HPA) to barrier-to-autointegration factor (BANF1) [NX\_O75531](../entry/NX_O75531/proteomics)

##Changes to the SPARQL queries

**New queries**

The following query of interest to the rare disease community has been added:

* NXQ\_00294 **Variants in MECP2 causing Rett Syndrome**

to the [SNORQL](https://snorql.nextprot.org/) interface.

**Queries removed**

Due to problems with external SPARQL endpoints, the following federated queries have been removed from the SNORQL interface:

* NXQ\_00094 **Proteins which are targets of antipsychotic drugs and expressed in brain**
* NXQ\_00096 **Proteins which are targets of drugs for cardiac therapy**
* NXQ\_00263 **Human proteins with baker's yeast orthologs according to OMA**
* NXQ\_00274 **Proteins involved in coronaviruses/SARS-CoV-2 pathways that are drug targets according to DrugBank**
* NXQ\_00275 **Proteins targeted by chloroquine and their GOLD binary interactions with other human proteins**
* NXQ\_00277 **Drugs targeting FYN interactors**

##New predictions of protein functions

Function predictions for 1 additional entry ([NX\_P0C7W6](../entry/NX_P0C7W6/function-predictions)) are now available. This brings the total number of entries with function predictions to 29 entries. Entries with function predictions are listed in the [functional proteome project](../about/functional-proteome-project) page. 
