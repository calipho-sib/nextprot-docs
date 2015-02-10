#Simple search

Our basic, Google-like full text search allows you to search the data in neXtProt. To do so, simply type in your query and hit the search button. To clear the query box, click on the "x" in the query form. Suggestions shown below the query box correspond to text found in neXtProt entries. 

##Query construction

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
