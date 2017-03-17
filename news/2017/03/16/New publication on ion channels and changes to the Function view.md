##New publication

**Annotation of functional impact of voltage-gated sodium channel mutations**

Hinard V, Britan A, Schaeffer M, Zahn-Zabal M, Thomet U, Rougier JS, Bairoch A, Abriel H, Gaudet P.

Hum Mutat. 2017 Feb 7. [doi: 10.1002/humu.23191](dx.doi.org/10.1002/humu.23191)

Abstract

Voltage-gated sodium channels are pore-forming transmembrane proteins that selectively allow sodium ions to flow across the plasma membrane according to the electro-chemical gradient thus mediating the rising phase of action potentials in excitable cells and playing key roles in physiological processes such as neurotransmission, skeletal muscle contraction, heart rhythm, and pain sensation. Genetic variations in the nine human genes encoding these channels are known to cause a large range of diseases affecting the nervous and cardiac systems. Understanding the molecular effect of genetic variations is critical for elucidating the pathologic mechanisms of known variations and in predicting the effect of newly discovered ones. To this end, we have created a Web-based tool, the Ion Channels Variants Portal, which compiles all variants characterized functionally in the human sodium channel genes. This portal describes 672 variants each associated with at least one molecular or clinical phenotypic impact, for a total of 4,658 observations extracted from 264 different research articles. These data were captured as structured annotations using standardized vocabularies and ontologies, such as the Gene Ontology and the Ion Channel ElectroPhysiology Ontology. All these data are available to the scientific community via neXtProt at [https://www.nextprot.org/portals/navmut](https://www.nextprot.org/portals/navmut).

##Updated Function view for entries

The Function view provides an overview of the molecular function of the entry, including its enzymatic activity and biophysicochemical properties. The biological processes and pathways in which the entry plays a role are also provided. In addition to modernizing this page so that it loads more quickly, a number of changes have been implemented to improve usability.

_New ENZYMATIC ACTIVITY sub-category_

This new sub-category regroups information concerning the enzymatic activity of the entry. In particular, the (1) reactions catalyzed, (2) enzymatic activity regulation and (3) cofactors required are now found in this section.

_Keyword definitions can now be viewed_

A &#34;Definition&#34; button has been added so that the definition for a keyword can be viewed without needing to leave the page.

_Changes to cross-references_

Some cross-references used to be interspersed throughout the section containing annotations. Some of these have been moved to the &#34;Further external links&#34; section at the bottom of the page, while others have been converted into annotations.

##Changes to the data model and files on the FTP site

Cross-references from TCDB have been converted into _transport-activity_ annotations. As the neXtProt data model has changed, the ttl files have been regenerated and are available on the FTP site at [ftp://ftp.nextprot.org/pub/current\_release/rdf/ttl/](ftp://ftp.nextprot.org/pub/current_release/rdf/ttl/). A new annotation category has been added to the XSD file and the XML files regenerated; these files are available at [ftp://ftp.nextprot.org/pub/current\_release/xml/](ftp://ftp.nextprot.org/pub/current_release/xml/).

##New advanced search SPARQL queries

The following queries have been added:

* [NXQ_00218](/proteins/search?mode=advanced&queryId=NXQ_00218) Proteins for which different splice isoforms have a different subcellular location or function
* [NXQ_00220](/proteins/search?mode=advanced&queryId=NXQ_00220) Proteins located on chromosome MT (mitochondrial) coded by a gene located on the plus strand

The first query illustrates that isoform-specific differences can be retrieved. The second query shows that the majority of genes located on the mitochondrion are located on the plus strand. 
