##DSDMap project

Dravet syndrome (DS) is a rare disease causing epileptic seizures and neurodevelopmental problems. It is usually caused by pathogenic mutations in the SCN1A gene, which codes for a Na+ transporter protein. Like for many other rare genetic disorders, the molecular mechanisms of DS are poorly understood, and therapeutic success with available drugs is limited. 

The neXtProt team at the SIB Swiss Institute of Bioinformatics is happy to announce it is partnering with [Maastricht University](https://www.maastrichtuniversity.nl/) in The Netherlands, the [Ludwig-Maximilians-University](https://www.lmu.de/en/) in Germany and the [Dravet Syndrome Foundation Spain](https://dravetfoundation.eu/) in a new project. The study aims to create a DS Disease Map (DSDMap), an interactive, machine-readable, molecular network. The DSDMap, created and curated by an interdisciplinary consortium of bioinformaticians, biomedical and clinical researchers together with a patient organization, will support investigators in the discovery of new potential treatment options for DS, as well as facilitate the search for relevant, currently unknown biomarkers of DS, useful for diagnosis and allowing prediction and evaluation of treatment success, and improvement of prognosis.

##Changes to the data

This release, neXtProt data release 2022-05-19, incorporates new variants, bringing the total number of variants in neXtProt to 9720110. 

**New variants causing Dravet syndrome**

Our team has started annotating [SCN1A](../entry/NX_P35498/medical) variants causing DS from the literature and integrating them in neXtProt. 

**New variants observed in patients with 272 different diseases**

Genetic variants which have been identified in patients but for which the causal relationship is not established were annotated from the literature by our team. A total of 2189 variants in 169 entries were integrated.

##New predictions of protein functions

Function predictions for 48 new entries are now available, bringing the total number of entries with predictions to 80. Some were proposed by Bachelor students who took part in the 2022 edition of the [Data mining for protein function prediction: Fonctionathon](https://www.unige.ch/innovations-pedagogiques/innovations/fonctionathon) course at the University of Geneva.

All entries with function predictions are listed [here](https://www.nextprot.org/proteins/search?listId=RGGSN4W1). 

##Changes to SPARQL queries

**New SPARQL queries**

The following queries of interest to the Dravet community have been added:

* NXQ\_00295 **References for SCN1A variants causing Dravet syndrome** Clinicians should use this query to find missing publications describing variants not found in neXtProt and submit these using the Contact option.
* NXQ\_00296 **Pathways in which SCN1A GOLD interactants are involved** This query may be of interest to scientists studying Dravet syndrome.

An additional query of interest to structural biologists has been added:

* NXQ\_00297 **PDB structures spanning the complete sequence of the mature protein**

All these queries are found in the [SNORQL](https://snorql.nextprot.org/) interface.

**Modified SPARQL queries**

The SPARQL query examples NXQ_00255, NXQ_00271, and NXQ_00256 have been updated to take into account the changes in the naming of RDF entities (see below). 

Queries NXQ_00134 and NXQ_00141 have been removed as they no longer returns results. 

##Changes to the RDF

The following entities have been renamed:

1. _:allele-count_ to _:alleleCount_
2. _:allele-frequency_ to _:alleleFrequency_
3. _:allele-number_ to _:alleleNumber_
4. _:homozygote-count_ to _:homozygoteCount_

If your private queries include these entitites, please update them as otherwise they will not return results.
