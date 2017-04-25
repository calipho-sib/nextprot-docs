##Changes to the data

This release incorporates the data from UniProtKB 2017_04, as well as updates of Ensembl, COSMIC, IntAct, and GO. Annotations from four new GO Consortium members, ARUK-UCL, CAFA, SynGO, and SynGO are now in neXtProt.

##Phenotypes affecting electrophysiological parameters are now displayed in the Phenotypes view

Voltage-gated sodium channels are pore-forming transmembrane proteins that selectively allow sodium ions to flow across the plasma membrane according to the electro-chemical gradient thus mediating the rising phase of action potentials in excitable cells and playing key roles in physiological processes such as neurotransmission, skeletal muscle contraction, heart rhythm, and pain sensation. The molecular effect of sequence variations in the nine human genes encoding these channels ([SCN1A](/entry/NX_P35498/phenotypes), [SCN2A](/entry/NX_Q99250/phenotypes), [SCN3A](/entry/NX_Q9NY46/phenotypes), [SCN4A](/entry/NX_P35499/phenotypes), [SCN5A](/entry/NX_Q14524/phenotypes), [SCN8A](/entry/NX_Q9UQD0/phenotypes), [SCN9A](/entry/NX_Q15858/phenotypes), [SCN10A](/entry/NX_Q9Y5Y9/phenotypes), [SCN11A](/entry/NX_Q9UI33/phenotypes)) on electrophysiological parameters are now shown in the Phenotypes view. The electrophysiological parameters are described using the Ion Channel ElectroPhysiology Ontology [ICEPO](https://academic.oup.com/database/article-lookup/doi/10.1093/database/baw017) developed in-house and downloadable from [ftp://ftp.nextprot.org/pub/current\_release/controlled_vocabularies/icepo.obo](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/icepo.obo).

##Revamped Interactions view

The Interactions view provides information concerning molecules (other human proteins, non-human proteins, drugs or chemicals) interacting directly with the protein represented in an entry. In addition to improving performance, a number of changes have been implemented to improve usability:
1.	Additional positional features: Calcium binding regions, DNA binding regions, nucleotide phosphate binding regions, miscellaneous regions describing binding, binding sites, and metal binding sites.
2.	New sections: ENZYME REGULATION, GO BINDING (GO molecular function annotations concerning binding), GO RECEPTOR ACTIVITY (GO molecular function annotations concerning receptor activity), PROTEIN-COFACTOR INTERACTION and PROTEIN-DRUG INTERACTION.
3.	Interactants in the PROTEIN-PROTEIN INTERACTION section are now listed in the order: (i) Itself (ii) Gene name, irrespective of the species, in alphabetical order for other interactants, (iii) Interactants with no gene name, i.e. for which the gene name is given as &#34;-&#34;.

##Changes to the data model and files on the FTP site

A new annotation type _cofactor-info_ was created which contains the text of the UniProtKB &#39;Cofactor&#39; annotation block &#34;Note&#34;. This change in the neXtProt data model is reflected in the ttl files at [ftp://ftp.nextprot.org/pub/current\_release/rdf/ttl/](ftp://ftp.nextprot.org/pub/current_release/rdf/ttl/), as well as in the XSD and XML files at [ftp://ftp.nextprot.org/pub/current\_release/xml/](ftp://ftp.nextprot.org/pub/current_release/xml/).

##New advanced search SPARQL queries

The following query has been added:

* [NXQ_00219](/proteins/search?mode=advanced&queryId=NXQ_00219) Proteins entries from a list of gene names

This query illustrates the use of a list in a query. 
