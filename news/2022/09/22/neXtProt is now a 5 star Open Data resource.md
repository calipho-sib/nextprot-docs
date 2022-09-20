##Changes to the neXtProt RDF

The Resource Description Framework (RDF) is a standard model for data interchange on the Web.   

**Changes to the RDF model**

The neXtProt model and documentation has been completely revised.

**Missing, undefined and unused entities**

Missing or undefined entities reported by one of our users have been dealt with, improving the consistency of our RDF data:

* The missing source TCDB ([Transport Classification Database](https://www.tcdb.org)) used to describe transporters has been added. 
* The undefined terminology type UniprotFamilyCv has been removed. 
* Unused entities have also been removed from the model for improved usability. 

Missing annotations will be added in the next data release.

**Changes to names**

Depending on whether it refers to the name of a protein entry, a gene or an isoform, names are now modeled in a semantically-correct fashion:

_Protein names_

Recommended protein names were previous queried using ```?entry :recommendedName /:fullName ?name .```<br>
It is now necessary to specify that the recommended name refers to a protein name as follows:<br>
```?entry :recommendedName ?name_entity .```<br>
```?name_entity a :ProteinName; rdfs:label ?name .```<br>
Example: [NXQ\_00290](../proteins/search?mode=advanced&queryId=NXQ_00290)<br>
For more information, refer to the help page for the entity [:Entry](https://snorql.nextprot.org/help/entity/Entry).<br>

_Gene names_

Gene names used to be specified using ```?entry :gene / :name ?name .```<br>
It is now necessary to add / rdfs:label after :name to have:<br>
```?entry :gene / :name / rdfs:label ?name .```<br>
Note that gene name are also directly connected to the gene entities themselves with recommended, alternative and ORF names, i.e. :<br>
```?gene :name / rdfs:label ?name .```<br>
Example: [NXQ\_00047](../proteins/search?mode=advanced&queryId=NXQ_00047)<br>
For more information, refer to the help page for the entity [:Gene](https://snorql.nextprot.org/help/entity/Gene).<br>

_Isoform names_

Isoform names were not previously exposed in our RDF. They can now be retrieved by specifying that the name, or more specifically the recommended or alternative name refers to an isoform name as follows:<br>
```?isoform :recommendedName ?name_entity .```<br>
```?name_entity a :IsoformName; rdfs:label ?name .```<br>
Example: New SPARQL query NXQ\_00298 in the [SNORQL interface](https://snorql.nextprot.org/).<br>
For more information, refer to the help page for the entity [:Isoform](https://snorql.nextprot.org/help/entity/Isoform).<br>

**Changes to terms**

All controlled vocabulary or ontology terms used in neXtProt are now modeled in a simplified manner. !! TO DO PAM !!

**Improved documentation**

The simplified view of the neXtProt data model has been updated both in the [Search](../help/data-model) and [SNORQL](https://snorql.nextprot.org/help/doc/introduction) user interfaces. This visual guide to the neXtProt data model is useful for beginners wishing to go beyond modifying the SPARQL query examples provided. A link to the textual documentation is also provided for power users wanting to exploit the neXtProt RDF.

The full, textual documentation is now available at [http://www.nextprot.org/rdf](http://www.nextprot.org/rdf). 

##Changes to the export files

All the RDF changes described above are implemented in the schema file which can be downloaded from [https://download.nextprot.org/pub/current\_release/rdf/ttl/schema.ttl.gz](https://download.nextprot.org/pub/current_release/rdf/ttl/schema.ttl.gz). 

##Changes to SPARQL queries

To make it easy for users who are unfamiliar with SPARQL to understand the query syntax, comments (preceded by #) have been added to the first 5 sample queries ([NXQ\_00001](../proteins/search?mode=advanced&queryId=NXQ_00001),  [NXQ\_00002](../proteins/search?mode=advanced&queryId=NXQ_00002), [NXQ\_00003](../proteins/search?mode=advanced&queryId=NXQ_00003), [NXQ\_00004](../proteins/search?mode=advanced&queryId=NXQ_00004) and [NXQ\_00005](../proteins/search?mode=advanced&queryId=NXQ_00005)).

All query examples have been checked and modified, if necessary. **Please modify your saved queries accordingly.**

##A 5 star Open Data resource

To date, neXtProt was:

&#11088; Available on the Web (whatever format) under the open license CC BY 4.0 since February 21, 2018.<br>
&#11088;&#11088; Available as structured data since its first release on August 23, 2011.<br>
&#11088;&#11088;&#11088; Available in the non-proprietary open format XML since its first release on August 23, 2011.

As of today, neXtProt:

&#11088;&#11088;&#11088;&#11088; Uses URIs to denote things through dereferencing.<br>
&#11088;&#11088;&#11088;&#11088;&#11088; Links neXtProt data to other data, i.e. UniProt entries, to provide context.

**So, start linking to our data and let's build the semantic web of human proteins together!**

If you have questions or run into problems, please don't hesitate to contact us.
