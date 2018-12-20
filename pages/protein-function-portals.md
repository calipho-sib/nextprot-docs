# Documentation

This portal provides information about the function of proteins. Annotation statements are triplets composed of (1) a **subject**, which corresponds to a protein being annotated; (2) a **relation** describing how the property is affected, and (3) an **object** that describes the function, localization, or protein property being tested.
 

## Column definition

* **Protein**: Subject of the annotation, corresponding to a protein 

* **Relation**: In-house [relations vocabulary](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/cv_modification_effect.obo) describing the type of effect of the protein. 

* **Negative**: Specify if the annotation is a negative annotation 

* **Function**: Object of the annotation triplet, describing: 
 * Effect on protein function/biological process/cellular localization, captured with [Gene Ontology](http://www.geneontology.org/) terms.
 * Effect on binding to proteins and protein complexes, captured with neXtProt entry IDs.
 * Effect on binding to chemicals, captured with [ChEBI](https://www.ebi.ac.uk/chebi/) terms.
 * Effect on electrophysiological parameters, captured with [ICEPO ontology](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/icepo.obo).
 * Effect on protein property (abundance, degradation, etc.), captured with in-house [protein properties vocabulary](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/cv_protein_property.obo).
 * Abnormal phenotypes, captured with [Mammalian Phenotype ontology](http://www.informatics.jax.org/searches/MP_form.shtml) terms.

* **Data confidence**: Evidence is tagged **Gold** or **Silver** according to curator judgment, based on statistical significance, the relevance of the assay, or other criteria.

* **Evidence codes**: Terms describing the experimental protocols supporting the evidence captured using the [Evidence and Conclusion Ontology](http://evidenceontology.org/Welcome.html).

* **Reference**: [PubMed ID](http://www.ncbi.nlm.nih.gov/pubmed) reference or [digital object identifier (DOI)](https://www.doi.org/) of the study supporting the evidence. 

* **Protein Origin**: Species from which the protein being studied was derived, captured with the [NCBI taxomomy](https://www.ncbi.nlm.nih.gov/taxonomy). Note that it is different from the experimental system (see below).

* **Cell line / Tissue**: Cell type or tissue from the [CALOHA human anatomy vocabulary](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/caloha.obo) or the cell line from the [Cellosaurus knowledge resource](http://web.expasy.org/cellosaurus/) that was used in the experiment. Empty for *in vitro* experiments.

* **Experimental system**: Species in which the mutated protein is studied, captured with the [NCBI taxomomy](https://www.ncbi.nlm.nih.gov/taxonomy). For example, a mouse protein [protein origin = Mus musculus] can be studied in a human cell line [Experimental system = Homo sapiens]. *In vitro* studies are annotated as "None (*in vitro*)". 

* **Experimental details**: Curator note adding relevant information about the evidence.

## References

Cusin I, Teixeira D, Zahn-Zabal M, Rech de Laval V, Gleizes A, Viassolo V, Chappuis PO, Hutter P, Bairoch A, Gaudet P. **A new bioinformatics tool to help assess the significance of BRCA1 variants.** Hum Genomics. 2018 Jul 11;12(1):36. [doi: 10.1186/s40246-018-0168-0](http://dx.doi.org/10.1186/s40246-018-0168-0).

Hinard V, Britan A, Schaeffer M, Zahn-Zabal M, Thomet U, Rougier JS, Bairoch A, Abriel H, Gaudet P. **Annotation of functional impact of voltage-gated sodium channel mutations.** Hum Mutat. 2017 Feb 7. [doi: 10.1002/humu.23191](http://dx.doi.org/10.1002/humu.23191).

## Comments & Feedback
If you have any comments or feedback, write to support @ nextprot.org. 
