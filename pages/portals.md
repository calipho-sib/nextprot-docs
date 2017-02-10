# Documentation

This portal provides information about the functional impact of genetic variants and artificially generated mutants. Annotation statements are triplets composed of (1) a **subject**, which corresponds to the protein variant being annotated; (2) a **relation** describing how the property is affected, and (3) an **object** that describes the function, localization, or protein property being tested.
 

## Column definition

* **Position**: Position of the mutation on the protein sequence. 

* **Protein Variant**: Subject of the annotation, corresponding to a protein mutation named according to [HGVS nomenclature](http://varnomen.hgvs.org/recommendations/protein/). Variants are annotated to the canonical sequence or to the specific isoforms sequence. In this case, the protein mutation name will contain "-iso". 

* **Mutation type**: Consequence of the mutation on the protein using [Sequence Ontology terms](http://www.sequenceontology.org). 

* **Mutation origin**: Either inherited mutation (germline variant), acquired mutation (somatic variant) or artificial (mutated variant site) using Sequence Ontology terms. 

* **Phenotype intensity**: Grade of the functional defect/phenotype observed: **Severe**, **Moderate**, **Mild**, or **Not Applicable (N/A)** when the mutant has no significant impact. The criteria are based on the fold-change of activity, response, etc., in the mutant compared to the control: 
 * Severe: over 80% 
 * Moderate: 20 to 80%
 * Mild: 10 to 20%

* **Relation**: In-house [relations vocabulary](ftp://ftp.nextprot.org/pub/current\_release/controlled\_vocabularies/cv\_modification\_effect.obo) describing the type of effect of the mutation. 

* **Function**: Object of the annotation triplet, describing: 
 * Effect on protein function/biological process/cellular localization, captured with [Gene Ontology terms](http://www.geneontology.org/).
 * Effect on binding to proteins and protein complexes, captured with neXtProt entry IDs.
 * Effect on binding to chemicals, captured with [ChEBI terms](https://www.ebi.ac.uk/chebi/).
 * Effect on electrophysiological parameters, captured with [ICEPO ontology](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/icepo.obo).
 * Effect on protein property (abundance, degradation, etc.), captured with in-house [protein properties vocabulary](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/cv_protein_property.obo).
 * Abnormal phenotypes, captured with [Mammalian Phenotype ontology](http://www.informatics.jax.org/searches/MP_form.shtml) terms.

* **Data confidence**: Evidence is tagged **Gold** or **Silver** according to curator judgment, based on statistical significance, the relevance of the assay, or other criteria.

* **Evidence codes**: Terms describing the experimental protocols supporting the evidence captured using the [Evidence and Conclusion Ontology](http://evidenceontology.org/Welcome.html).

* **Reference**: [PubMed ID](http://www.ncbi.nlm.nih.gov/pubmed) reference or [digital object identifier (DOI)](https://www.doi.org/) of the study supporting the evidence. 

* **Protein Origin**: Species from which the protein being studied was derived. Note that it is different from the experimental system (see below).

* **Cell line / Tissue**: Cell type or tissue from the [CALOHA human anatomy vocabulary](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/caloha.obo) or the cell line from the [Cellosaurus knowledge resource](http://web.expasy.org/cellosaurus/) that was used in the experiment. Empty for *in vitro* experiments.

* **Experimental system**: Species in which the mutated protein is studied. For example, a mouse protein [protein origin = Mus musculus] can be studied in a human cell line [Experimental system = Homo sapiens]. *In vitro* studies are annotated as "None (*in vitro*)". 

* **Experimental details**: Curator note adding relevant information about the evidence.

## Comments & Feedback
If you have any comments or feedback, write to support @ nextprot.org. 
