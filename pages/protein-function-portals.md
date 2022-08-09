# Documentation

This portal provides information about the function of proteins. Annotation statements are triplets composed of (1) a **subject**, which corresponds to a protein being annotated; (2) a **relation** describing how the property is affected, and (3) an **object** that describes the function, localization, or protein property being tested.
 

## Column definition

* **Accession number**: Accession number(s) of the subject of the annotation.

* **Protein**: Subject of the annotation, corresponding to a protein 

* **Relation**: In-house [relations vocabulary](https://download.nextprot.org/pub/current_release/controlled_vocabularies/cv_modification_effect.obo) describing the type of effect of the protein. 

* **Negative**: Specify if the annotation is a negative annotation 

* **Function**: Object of the annotation triplet, describing: 
  * Protein's molecular function/biological process/cellular localization, captured with [Gene Ontology](http://www.geneontology.org/) terms.
  * Protein's binding partners (both proteins and protein complexes), captured with neXtProt entry IDs, and with [ChEBI](https://www.ebi.ac.uk/chebi/) terms for chemicals.

* **Data confidence**: Evidence is tagged **Gold** or **Silver** according to curator judgment, based on statistical significance, the relevance of the assay, or other criteria.

* **Evidence codes**: Terms describing the experimental protocols supporting the evidence captured using the [Evidence and Conclusion Ontology](http://evidenceontology.org/Welcome.html).

* **Reference**: [PubMed ID](http://www.ncbi.nlm.nih.gov/pubmed) reference or [digital object identifier (DOI)](https://www.doi.org/) of the study supporting the evidence. 

* **Protein Origin**: Species from which the protein being studied was derived, captured with the [NCBI taxomomy](https://www.ncbi.nlm.nih.gov/taxonomy). Note that it is different from the experimental system (see below).

* **Cell line / Tissue**: Cell type or tissue from the [CALOHA human anatomy vocabulary](https://download.nextprot.org/pub/current_release/controlled_vocabularies/caloha.obo) or the cell line from the [Cellosaurus knowledge resource](http://web.expasy.org/cellosaurus/) that was used in the experiment. Empty for *in vitro* experiments.

* **Experimental system**: Species in which the mutated protein is studied, captured with the [NCBI taxomomy](https://www.ncbi.nlm.nih.gov/taxonomy). For example, a mouse protein [protein origin = Mus musculus] can be studied in a human cell line [Experimental system = Homo sapiens]. *In vitro* studies are annotated as "None (*in vitro*)". 

* **Experimental details**: Curator note adding relevant information about the evidence.

## References

Cicenas J, Zalyte E, Bairoch A, Gaudet P. **Kinases and Cancer.** Cancers (Basel). 2018 Mar 1;10(3). pii: E63. [doi: 10.3390/cancers10030063](http://dx.doi.org/10.3390/cancers10030063).

Gaudet P, Michel PA, Zahn-Zabal M, Britan A, Cusin I, Domagalski M, Duek PD, Gateau A, Gleizes A, Hinard V, Rech de Laval V, Lin J, Nikitin F, Schaeffer M, Teixeira D, Lane L, Bairoch A. **The neXtProt knowledgebase on human proteins: 2017 update.** Nucleic Acids Res. 2017 Jan 4;45(D1):D177-D182. [doi:10.1093/nar/gkw1062](http://dx.doi.org/10.1093/nar/gkw1062).

## Comments & Feedback
If you have any comments or feedback, write to support @ nextprot.org. 
