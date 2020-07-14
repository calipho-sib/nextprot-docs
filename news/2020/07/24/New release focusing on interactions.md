This release, neXtProt data release 2020-07-??, is the first time neXtProt integrates data from a biotech company.

##Changes to the data

**New interaction data**

Human protein- protein interactions (PPIs) manually annotated from the literature from [ENYO Pharma SA](http://www.enyopharma.com/technology/interactome-datasets/) have been included. Interactions between two proteins have been incorporated as binary interaction annotations. When the _sequence_ describing the region mediating the protein-protein interaction experimentally is known, the interactions have been integrated in the new interaction mapping (RDF entity [:interactionMapping](https://snorql.nextprot.org/help/entity/InteractionMapping)) annotations. This is to distinguish them from the region annotations (:interactingRegion) from [UniProt](https://www.uniprot.org/) describing, in some cases, the _minimal region_ required to mediate a protein-protein interaction experimentally. Interaction mapping annotations are displayed in the track labelled &quot;Exp. interaction&quot; in the Interactions view. Example: NX_?

For all interaction annotations, ENYO captured the experimental method using the PSI [Molecular Interactions](https://www.ebi.ac.uk/ols/ontologies/mi) (PSI-MI) controlled vocabulary. The PSI-MI term is displayed in all evidences from ENYO. In order to have a coherent corpus of data in neXtProt, an ECO code is also provided for each evidence from ENYO.

A total of ? entries contain interaction data from ENYO, curated from? publications. While the vast majority, ?, have binary interaction annotations, ? entries have annotations specifying the region that was experimentally shown to be involved in the interaction.    

**Updated data**

Data from UniProtKB, dbSNP, IntAct, GOA, GlyConnect, gnomAD and neXtProt have also been updated. 

##Changes to the export files

**Changes to the XML**

Our XSD file available at [ftp://ftp.nextprot.org/pub/current\_release/xml/nextprot-export-v2.xsd](ftp://ftp.nextprot.org/pub/current_release/xml/nextprot-export-v2.xsd) has been updated to take into account the new interaction mapping annotations. The changes are documented in a comment at the beginning of the XSD file.

##Changes to advanced search SPARQL queries

New queries have been added that illustrate how to query interaction data in neXtProt:

•	NXQ_00277 
•	NXQ_00278
•	NXQ_00279

As we no longer have the evidence code (ECO) in the experimental context (:ExperimentalContext) in our RDF, queries NXQ_00020, NXQ_00077, NXQ_00221, NXQ_00222, NXQ_00235 and NXQ_00273 have been modified to use the ECO (:evidenceCode) found in the evidence.

Finally, the federated queries with [ChEMBL](https://www.ebi.ac.uk/chembl/), NXQ_00139, NXQ_00266 and NXQ_00267, have been removed as they no longer return results.
