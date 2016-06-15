# Portals
These portals provide information about the functional impact of genetic variants and artificially generated mutants.  


## Column definition

* **Position**: Position of the mutation on the canonical protein sequence. The position is only shown for variants annotated to the canonical sequence. However, some variants are related to a specific isoform, indicated in the protein mutation name, which will contain "-iso". In this case, no position is indicated in the 'Position' column.

* **Protein Variant**: Protein mutation name according to HGVS nomenclature [http://varnomen.hgvs.org/recommendations/protein/](http://varnomen.hgvs.org/recommendations/protein/).

* **Mutation type**: The mutation type describes the impact of the mutation on the protein, according to Sequence Ontology [http://www.sequenceontology.org](http://www.sequenceontology.org).

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


