This release, neXtProt data release 2020-07-17, is the first time neXtProt integrates data from a biotech company.

##Changes to the data

**New interaction data**

Human protein- protein interactions (PPIs) manually annotated from the literature from [ENYO Pharma SA](http://www.enyopharma.com/technology/interactome-datasets/) have been included. Interactions between two proteins have been incorporated as binary interaction annotations. When the _sequence_ used in the protein-protein interaction experiment is known, the interactions have been integrated in the new interaction mapping (RDF entity [:interactionMapping](https://snorql.nextprot.org/help/entity/InteractionMapping)) annotations. This is to distinguish them from the region annotations (:interactingRegion) from [UniProt](https://www.uniprot.org/) describing, in some cases, the _minimal region_ required to mediate a protein-protein interaction. Interaction mapping annotations are displayed in the track labelled &quot;Exp. interaction&quot; in the Interactions view. Example: Dual specificity mitogen-activated protein kinase kinase 1 (MAP2K1) [[NX\_Q02750](../entry/NX_Q02750/interactions)]

For all interaction annotations, ENYO captured the experimental method using the PSI [Molecular Interactions](https://www.ebi.ac.uk/ols/ontologies/mi) (PSI-MI) controlled vocabulary. The PSI-MI term is displayed in all evidences from ENYO. In order to have a coherent corpus of data in neXtProt, the ECO term physical interaction evidence used in manual assertion (ECO:0000353) was assigned to each evidence from ENYO.

A total of 12961 entries contain interaction data from ENYO, curated from 324 publications. While all 12961 entries have binary interaction annotations, 2170 entries have annotations specifying the region that was experimentally shown to be involved in the interaction.    

**Updated data**

Data from UniProtKB, Ensembl, IntAct, GOA, GlyConnect, gnomAD and neXtProt have also been updated. 

##Changes to the export files

**Changes to the XML**

Our XSD file available at [ftp://ftp.nextprot.org/pub/current\_release/xml/nextprot-export-v2.xsd](ftp://ftp.nextprot.org/pub/current_release/xml/nextprot-export-v2.xsd) has been updated to take into account the new interaction mapping annotations. The changes are documented in a comment at the beginning of the XSD file.

##Changes to advanced search SPARQL queries

New queries have been added in the [SnorQL](https://snorql.nextprot.org/) interface that illustrate how to query interaction data in neXtProt:

1. NXQ\_00277 **Drugs targeting FYN interactors** 
2. NXQ\_00278 **Authors who have reported more than 25000 human protein-protein interactions**
3. NXQ\_00279 **Proteins for which an interaction mapping region is described for both interactants**
4. NXQ\_00280 **Proteins interacting with at least 10 members of a protein family**

We used to have the evidence code (ECO) both in the experimental context (:ExperimentalContext) and in the evidence (:Evidence). To avoid confusion, we have removed it from the experimental context in our RDF and updated queries NXQ\_00020, NXQ\_00077, NXQ\_00221, NXQ\_00222, NXQ\_00235 and NXQ\_00273.

Finally, the federated queries with [ChEMBL](https://www.ebi.ac.uk/chembl/), NXQ\_00139, NXQ\_00266 and NXQ\_00267, have been removed as they no longer return results.
