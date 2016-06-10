# Portals
These portals provide information about the functional impact of genetic variants and artificially generated mutants.  


## Column definition

* **Position** : Position of the mutation on protein sequence.

* **Protein Variant** : Protein mutation description name according to HGVS nomenclature http://varnomen.hgvs.org/recommendations/protein/


* **Mutation type**: The mutation type describes the impact of the mutation on the protein, according to Sequence Ontology http://www.sequenceontology.org 


* **Mutation origin**:  The mutation origin describes either inherited mutation (germline_variant), acquired mutation (somatic_variant), or artificial (mutated_variant_site) according to Sequence Ontology http://www.sequenceontology.org 

* **Relation**: In-house relations describing the functional defect/phenotype (Impact), or the absence of functional defect/phenotype (No impact)

* **Function**: 
-	Effect on protein function/process/cellular localization is captured with Gene Ontology terms
-	Effect on binding to proteins and protein complexes is captured with neXtProt entry IDs
-	Effect on binding to chemicals is captured with CHEBI terms
-	Effect on electrophysiological parameters are captured with the ICEPO ontology (relevant to ion channels)


* **Phenotype intensity**: Amplitude of the functional defect/phenotype observed: severe, moderate, or mild. Not applicable for observation where the mutant has no significant impact: N/A


* **Data confidence**: Annotations are tagged “Gold” or “Silver” according to curator judgment


* **Evidence codes**: Terms describing the experimental protocols supporting the evidence http://www.evidenceontology.org/


* **Reference**: Pubmed ID reference of the study supporting the annotation http://www.ncbi.nlm.nih.gov/pubmed


* **Protein Origin**: Organism species from which the protein being studied was derived. Note that it is different from the experimental system (see below)


* **Experimental system**: Organism species of the model in which the mutated protein is studied, such as cell lines, primary cells and whole organism. In vitro studies are annotated as “None (in vitro)”. 









