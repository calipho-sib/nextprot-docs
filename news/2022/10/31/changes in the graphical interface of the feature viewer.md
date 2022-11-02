## Feature viewer improvements

The graphical interface of the feature viewer has been improved so that users can better visualize variant frequencies and peptide uniqueness.

- Variant frequency data from [gnomAD](https://gnomad.broadinstitute.org/) can now be viewed as a bar graph in the sequence, medical and structure views.<br>

    Example: [MECP2 sequence view](../entry/NX_P51608/sequence)

- Unique (green) and non unique (blue) peptides can now be easily distinguished in the Peptide and SRM peptide tracks of the proteomics and peptide views.

    Example: [FAM9A proteomics view](../entry/NX_Q8IZU1/proteomics)

## New predictions of protein functions

Function predictions for 19 new entries are now available, bringing the total number of entries with predictions to 223. <br>
All entries with function predictions are listed [here](../proteins/search?listId=9O74XY11).

## New SPARQL queries

Two new queries have been added to the [SNORQL](https://snorql.nextprot.org/) search interface 

The following query shows how to query recommended and alternative gene names with our new data model. For more information please see (https://www.nextprot.org/rdf/#Name)<br>
**NXQ_00046 Proteins with a gene alternative name starting with IL27** 

The following query shows how to extract a list of proteins with their small molecule interactants.<br>
**NXQ_00299 Proteins interacting with small molecules according to DrugBank**

