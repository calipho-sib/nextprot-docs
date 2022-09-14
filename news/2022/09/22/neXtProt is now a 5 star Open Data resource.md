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

1. Recommended protein names were previous queried using ```?entry :recommendedName /:fullName```

It is now necessary to specify that the recommended name refers to a protein name as follows:

```:recommendedName ?name_entity .```<br>
```?name_entity a :ProteinName; rdfs:label```

Example: [NXQ\_00290](../proteins/search?mode=advanced&queryId=NXQ_00290)
For more information, refer to the help page for the entity [:Entry](https://snorql.nextprot.org/help/entity/Entry).

2. Gene names used to be specified using ```:gene / :name```

It is now necessary to add / rdfs:label after :name to have:

```:gene / :name / rdfs:label```

Example: [NXQ\_00047](../proteins/search?mode=advanced&queryId=NXQ_00047)
For more information, refer to the help page for the entity [:Gene](https://snorql.nextprot.org/help/entity/Gene).

3. Isoform names were not previously exposed in our RDF. They can now be retrieved by specifying that the recommended name refers to an isoform name as follows:

```:recommendedName ?name_entity .```<br>
```?name_entity a :IsoformName; rdfs:label```

Example: !! ADD NEW query to retrieve entry isoform accessions and names !!
For more information, refer to the help page for the entity [:Isoform](https://snorql.nextprot.org/help/entity/Isoform).

**Changes to terms**

All controlled vocabulary or ontology terms used in neXtProt are now modeled in a simplified manner. !! TO DO PAM !!

**Improved documentation**

The simplified view of the neXtProt data model has been updated both in the [Search](../help/data-model) and [SNORQL](https://snorql.nextprot.org/help/doc/introduction) user interfaces. This visual guide to the neXtProt data model is useful for beginners wishing to go beyond modifying the SPARQL query examples provided. A link to the textual documentation is also provided for power users wanting to exploit the neXtProt RDF.

The full, textual documentation is now available at [http://www.nextprot.org/rdf](http://www.nextprot.org/rdf). 

##Changes to the export files

All the RDF changes described above are implemented in the schema file which can be downloaded from [https://download.nextprot.org/pub/current\_release/rdf/ttl/schema.ttl.gz](https://download.nextprot.org/pub/current_release/rdf/ttl/schema.ttl.gz). 

##Changes to SPARQL queries

All query examples have been checked and modified, if necessary. **Please modify your saved queries accordingly.**

To make it easy for users who are unfamiliar with SPARQL to understand the query syntax, comments (preceded by #) have been added to the first 5 sample queries:

1. [NXQ\_00001](../proteins/search?mode=advanced&queryId=NXQ_00001) **Proteins phosphorylated and located in the cytoplasm**
2. [NXQ\_00002](../proteins/search?mode=advanced&queryId=NXQ_00002) **Proteins that are located in both the nucleus and in the cytoplasm**
3. [NXQ\_00003](../proteins/search?mode=advanced&queryId=NXQ_00003) **Proteins with 7 transmembrane regions**
4. [NXQ\_00004](../proteins/search?mode=advanced&queryId=NXQ_00004) **Proteins expressed in brain with IHC expression level: "high" but not expressed in testis**
5. [NXQ\_00005](../proteins/search?mode=advanced&queryId=NXQ_00005) **Proteins located in mitochondrion and that lack a transit peptide** 

##A 5 star Open Data resource

To date, neXtProt was:

:star: Available on the Web (whatever format) under the open license CC BY 4.0 since February 21, 2018.<br>
:star::star: Available as structured data since its first release on August 23, 2011.<br>
:star::star::star: Available in the non-proprietary open format XML since its first release on August 23, 2011.

As of today, neXtProt:

:star::star::star::star: Uses URIs to denote things through dereferencing.<br>
:star::star::star::star::star: Links neXtProt data to other data, i.e. UniProt entries, to provide context.

**So, start linking to our data and let's build the semantic web of human proteins together!**

If you have questions or run into problems, please don't hesitate to contact us.
