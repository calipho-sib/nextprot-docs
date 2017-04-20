##Changes to the data

This release incorporates the data from UniProtKB 2017_04, as well as updates of Ensembl, COSMIC, IntAct, and GOA. Annotations from four new GO Consortium members, ARUK-UCL, CAFA, SynGO, and SynGO are now in neXtProt.

##Electrophysiology data is now displayed in the Phenotypes view

Voltage-gated sodium channels are pore-forming transmembrane proteins that selectively allow sodium ions to flow across the plasma membrane according to the electro-chemical gradient thus mediating the rising phase of action potentials in excitable cells and playing key roles in physiological processes such as neurotransmission, skeletal muscle contraction, heart rhythm, and pain sensation. The molecular effect of sequence variations in the nine human genes encoding these channels ([SCN1A](/entry/NX_P35498/phenotypes), [SCN2A](/entry/NX_Q99250/phenotypes), [SCN3A](/entry/NX_Q9NY46/phenotypes), [SCN4A](/entry/NX_P35499/phenotypes), [SCN5A](/entry/NX_Q14524/phenotypes), [SCN8A](/entry/NX_Q9UQD0/phenotypes), [SCN9A](/entry/NX_Q15858/phenotypes), [SCN10A](/entry/NX_Q9Y5Y9/phenotypes), [SCN11A](/entry/NX_Q9UI33/phenotypes)) on electrophysiological parameters are now shown in the Phenotypes view. The electrophysiological parameters are described using the Ion Channel ElectroPhysiology Ontology (ICEPO) developed in-house and downloadable from [ftp://ftp.nextprot.org/pub/current\_release/controlled_vocabularies/icepo.obo](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/icepo.obo).

##Revamped Interactions view for entries

The Interactions view provides information concerning molecules (other human proteins, non-human proteins, drugs or chemicals) interacting directly with the entry. In addition to updating this page so that it loads more quickly, a number of changes have been implemented to improve usability:
1.	A number of additional positional features are now shown in this view: Calcium binding regions, DNA binding regions, nucleotide phosphate binding regions, miscellaneous regions describing binding, binding sites, and metal binding sites.
2.	The following sections have been added: ENZYME REGULATION, GO BINDING (GO molecular function annotations concerning binding), GO RECEPTOR ACTIVITY (GO molecular function annotations concerning receptor activity), PROTEIN-COFACTOR INTERACTION and PROTEIN-DRUG INTERACTION.
3.	Interactants in the PROTEIN-PROTEIN INTERACTION section are now listed in the order: (i) Itself (ii) Gene name, irrespective of the species, in alphabetical order for other interactants, (iii) Interactants with no gene name, i.e. for which the gene name is given as "-".

##Changes to the data model and files on the FTP site

A new annotation type COFACTOR_INFO was created which contains the text of the UniProtKB ‘Cofactor’ annotation block “Note”. This change in the neXtProt data model is reflected in the [ttl](ftp://ftp.nextprot.org/pub/current_release/rdf/ttl/), [XSD and XML](ftp://ftp.nextprot.org/pub/current_release/xml/) files.
