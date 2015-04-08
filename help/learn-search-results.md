#Search results

While the search in the protein section makes use of the information in all isoforms, the results are provided as "entries" and not isoforms. 

Search results are shown in one of two formats: **Summary** and **Details (default).** The information displayed depends on the section being queried.

In the **Summary** format:

* **Proteins.** For each protein entry, the recommended protein name, the recommended gene name and the neXtProt entry accession code are displayed and link to the entry. The **downwards arrow** icon allows the entry to be downloaded. 
* **Publications.** For each publication, the title, first author name, journal name, volume, page numbers and year of publication are displayed. The **Show Abstract** button allows the abstract to be viewed. The first line links to the publication.
* **Terms.** For each term, the controlled vocabulary (CV) term, its accession code and its source (ontology) are displayed. The first line links to the term. 

In the **Details** format for **protein** search results:

* _first line_ is the same as in the Summary format, i.e. the recommended protein name, the recommended gene name and the neXtProt entry accession code are displayed and link to the entry. The **downwards arrow** icon allows the entry to be downloaded.
* _second line_ displays a snippet of text summarizing the function.
* _third line_ displays information concerning the protein entry: chromosomal location, number of isoforms, number of post-translational modifications (PTMs), sequence length and the number of variants.
* _last line_ summarizes whether or not there is disease, expression, mutagenesis, proteomics, 3D structure data for the entry, as well as its Proteins existence value.

In the **Details** format for **publications** search results:

* _first line_ is the same as in the Summary format, i.e. the title of the publication is displayed and links to the publication.
* _second line_ displays all the authors of the publication. Each author name links to a search for the publications by that author.
* _third line_ displays the citation data, ie. the journal name, volume, page numbers and year of publication are displayed. Links to the full text of the publication and to the citation data in PubMed are provided.
* The **Show Abstract** button allows the abstract to be viewed.

In the **Details** format for **terms** search results: 

* _first line_ is the same as in the Summary format, i.e. the controlled vocabulary (CV) term and its accession code are displayed and link to the term.
* _second line_ is the same as in the Summary format, i.e. the source of the term (ontology) is displayed.
* _third line_ displays the definition of the term.

#Filtering search results

Filtering options are displayed on the left and depend on the section being queried:

* **Proteins.** The entries displayed can be selected as having either 3D structure, disease, expression, mutagenesis, or proteomics data. 
* **Publications.** The publications displayed can be selected as having either "Cited for annotation", "Large scale data" or "Not cited for annotation". 
* **Terms.** The terms displayed can be selected based on their source. _Example_ Searching for [alzheimer](terms/search?query=alzheimer) returns terms from GO (Gene Ontology), MeSH (Medical Subject Headings), and UniProt, among others. Searching for "alzheimer" and filtering for [NCI Thesaurus](terms/search?query=alzheimer&filter=ncithesaurus) terms displays only terms found in the NCI Thesaurus which contain "alzheimer". To remove the filter, click on the "x" after the filter name.

#Sorting search results

Sorting options depend on the section being queried:

* **Proteins.** The entries displayed can be sorted in either _ascending or descending order_ of either the gene name, protein name, protein family name, chromosomal location, accession number (ACs), protein length or ranking score. 
* **Publications.** The publications displayed cannot be sorted. However they are displayed in descending order of year of publication. 
* **Terms.** The terms displayed can be sorted in either _ascending or descending order_ of either the term name or ranking score. 
