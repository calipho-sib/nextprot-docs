# Variant Functional Impact Portal
This portal provides information about the functional impact of genetic variants and artificially generated mutants. Annotation statements are triplets composed of (1) a **subject**, which corresponds to the protein variant being annotated; (2) a **relation** describing how the property is affected, and (3) an **object** that describes the function, localization, or protein property being tested.
 

## Column definition

* **Position**: •	Position of the mutation on the protein sequence. 

* **Protein Variant**: Subject of the annotation, corresponding to a protein mutation named according to HGVS nomenclature  [http://varnomen.hgvs.org/recommendations/protein/]HGVS nomenclature. Variants are annotated to the canonical sequence or to the specific isoforms sequence. In this case, the protein mutation name will contain "-iso". 

* **Mutation type**: Consequence of the mutation on the protein using Sequence Ontology terms [http://www.sequenceontology.org](http://www.sequenceontology.org).

* **Mutation origin**: The mutation origin describes either inherited mutation (germline variant), acquired mutation (somatic variant) or artificial (mutated variant site) according to Sequence Ontology. 

* **Phenotype intensity**: Amplitude of the functional defect/phenotype observed: Severe, Moderate or Mild. Not applicable for observation where the mutant has no significant impact: N/A or for annotations of electrophysiological parameters.

* **Relation**: In-house relations describing the functional defect/phenotype (Impact), or the absence of functional defect/phenotype (No impact).

* **Function**: 
  * Effect on protein function/biological process/cellular localization is captured with Gene Ontology terms
  * Effect on binding to proteins and protein complexes is captured with neXtProt entry IDs
  * Effect on binding to chemicals is captured with CHEBI terms
  * Effect on electrophysiological parameters is captured with the ICEPO ontology (relevant to ion channels) [ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/](ftp://ftp.nextprot.org/pub/current_release/controlled_vocabularies/)

* **Data confidence**: Evidence is tagged 'Gold' or 'Silver' according to curator judgment on the quality of the data.

* **Evidence codes**: Terms describing the experimental protocols supporting the evidence [http://www.evidenceontology.org/](http://www.evidenceontology.org/).

* **Reference**: Pubmed ID reference of the study supporting the evidence [http://www.ncbi.nlm.nih.gov/pubmed](http://www.ncbi.nlm.nih.gov/pubmed).

* **Protein Origin**: Organism species from which the protein being studied was derived. Note that it is different from the experimental system (see below).

* **Experimental system**: Organism species of the model in which the mutated protein is studied, such as cell lines, primary cells and whole organism. In vitro studies are annotated as "None (in vitro)". 

## Comments & Feedback
If you have any comments or feedback, write to support @ nextprot.org. 
