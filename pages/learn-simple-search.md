#neXtProt simple search cookbook

Our basic, Google-like full text search allows you to search the data in neXtProt. To do so, simply type in your query and hit the search button. To clear the query box, click on the "x" in the query form. Suggestions shown below the query box correspond to text found in neXtProt entries. 

## Query construction

You can search in **three separate sections**: 

* **Proteins (default).** Example: [insulin](http://alpha-search.nextprot.org/proteins/search?query=insulin)
* **Publications.** Example: [insulin](http://alpha-search.nextprot.org/publications/search?query=insulin)
* **Terms.** Example: [insulin](http://alpha-search.nextprot.org/terms/search?query=insulin)

To switch between sections, simply toggle between "Proteins", "Publications" and "Terms". Note that unless you clear the query box, your last query is kept in the search field. 

**Asterisks** can be used at the beginning and within terms. Note that terms starting with an asterisk or a single letter followed by an asterisk can slow down queries considerably.
_Example_: [insulin*](http://alpha-search.nextprot.org/proteins/search?query=insulin*) returns all entries containg terms starting with "insulin" (i.e. insulin, Insulinemia, etc.). 

If you enter **multiple terms**, the AND operator is applied by default.
_Example_: Searching for [Adrenocortical carcinoma](http://alpha-search.nextprot.org/proteins/search?query=Adrenocortical%20carcinoma) and [Adrenocortical and carcinoma](http://alpha-search.nextprot.org/proteins/search?query=Adrenocortical%20and%20carcinoma) return all entries containing both terms.

Searching for multiple terms enclosed in **quotes** returns all entries containing both terms in the exact order (exact term string).
_Example_: ["Adrenocortical carcinoma"](http://alpha-search.nextprot.org/proteins/search?query=%22Adrenocortical%20carcinoma%22)

**By default, only Gold quality data is searched.** To find entries with both Gold and Silver data matching the query, select "Include silver".
_Example_: Compare the results of searching for the Gene Ontology term  "Exocrine pancreas development" [GO:0031017 Gold only](http://alpha-search.nextprot.org/proteins/search?query=GO:0031017) and [GO:0031017 Include silver](http://alpha-search.nextprot.org/proteins/search?query=GO:0031017&quality=gold-and-silver).

## Search results

While the search in the protein section makes use of the information in all isoforms, the results are provided as “entries” and not isoforms. 

Search results are shown in one of two formats: **Summary** and **Details (default).**

In the **Summary** format, the information displayed depends on the section being queried:

* **Proteins.** For each protein entry, the recommended protein name, the recommended gene name and the neXtProt entry accession code are displayed and link to the entry.
* **Publications.** For each publication, the title and year of publication are displayed and link to the publication.
* **Terms.** For each term, the controlled vocabulary (CV) term and its accession code are displayed and link to the term. 

In the **Details** format, the information displayed differs only when querying for proteins:

* _first line_ is the same as in the Summary format, i.e. the recommended protein name, the recommended gene name and the neXtProt entry accession code are displayed and link to the entry.
* _second line_ displays a snippet of text summarizing the function.
* _third line_ displays information concerning the protein entry: chromosomal location, number of isoforms, number of post-translational modifications (PTMs), sequence length and the number of variants.
* _last line_ summarizes whether or not there is disease, expression, mutagenesis, proteomics, 3D structure data for the entry, as well as its Proteins existence value.

## Filtering search results

Filtering options depend on the section being queried:

* **Proteins.** The entries displayed can be selected as having either disease, expression, mutagenesis, proteomics or 3D structure data. 
* **Publications.** The publications displayed can be selected as having either "Not cited for annotation", "Cited for annotation" or "Large scale data". 
* **Terms.** The terms displayed can be selected based on their source. For example, searching for [alzheimer](http://alpha-search.nextprot.org/terms/search?query=alzheimer) returns terms from GO (Gene Ontology), MeSH (Medical Subject Headings), and UniProt, among others. Searching for "alzheimer" and filtering for [NCI Thesaurus](http://alpha-search.nextprot.org/terms/search?query=alzheimer&filter=ncithesaurus) terms displays only terms found in the NCI Thesaurus which contain "alzheimer". To remove the filter, click on the "x" after the filter name.

## Sorting search results

Sorting options depend on the section being queried:

* **Proteins.** The entries displayed can be sorted in either _ascending or descending order_ based on either the gene name, protein name, protein family name, chromosomal location, accession number (ACs), protein length or ranking score. 
* **Publications.** The publications displayed cannot be sorted. However they are displayed in descending order of year of publication. 
* **Terms.** The terms displayed can be sorted in either _ascending or descending order_ based on either the term name or ranking score. 
