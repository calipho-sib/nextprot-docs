This release, neXtProt data release 2022-05-19, incorporates new variants, bringing the total number of variants in neXtProt to 9720110. 

##Changes to the data

**New variants causing Dravet syndrome**

Dravet syndrome is a rare, lifelong form of epilepsy that begins in the first year of life. The disease, also known as Severe Myoclonic Epilepsy of Infancy (SMEI), can be caused by a genetic variation in the [SCN1A](../entry/NX_P35498/medical) gene. A total of 598 new SCN1A variants were annotated by our team and integrated, bringing the total number of SCN1A variants causing Dravet to 347 variants and ? variants which are observed in Dravet patients, but for which the evidence is not sufficient to support a causal relationship. 

**New variants observed in patients**

Genetic variants which have been identified in patients but for which the causal relationship is not established were annotated from the literature by our team. A total of ? variants in ? entries were integrated.

##Changes to the RDF

The following entities have been renamed:

1. _:allele-count_ to _:alleleCount_
2. _:allele-frequency_ to _:alleleFrequency_
3. _:allele-number_ to _:alleleNumber_
4. _:homozygote-count_ to _:homozygoteCount_

The SPARQL query examples NXQ_00255, NXQ_00271, and NXQ_00256 have been updated accordingly. If your private queries include these entitites, please update them as otherwise they will not return results.

##New advanced search SPARQL queries

The following queries of interest to the Dravet community have been added:

* NXQ\_00295 **References for SCN1A variants causing Dravet syndrome** Clinicians should use this query to submit missing publications describing variants not found in neXtProt.
* NXQ\_00296 **Pathways in which SCN1A GOLD interactants are involved** This query may be of interest to scientists studying Dravet syndrome.

An additional query of interest to structural biologists has been added:

* NXQ\_00297 **PDB structures spanning the complete sequence of the mature protein**

to the [SNORQL](https://snorql.nextprot.org/) interface.

##New predictions of protein functions

Function predictions for 48 new entries are now available, bringing the total number of entries with predictions to 80. Some were proposed by Bachelor students who took part in the 2022 edition of the [Data mining for protein function prediction: Fonctionathon](https://www.unige.ch/innovations-pedagogiques/innovations/fonctionathon) course at the University of Geneva.

All entries with function predictions are listed [here](https://www.nextprot.org/proteins/search?listId=RGGSN4W1). 
