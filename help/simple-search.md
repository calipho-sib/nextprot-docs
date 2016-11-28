
Our basic, Google-like full text search allows you to search the data in neXtProt. To do so, simply type in your query and hit the search button. To clear the query box, click on the "x" in the query form. Suggestions shown below the query box correspond to text found in neXtProt entries. 

##Query construction

You can search in **three separate sections**: 

* **Proteins (default).** Example: [insulin](proteins/search?query=insulin)
* **Publications.** Examples: [doolittle](publications/search?query=doolittle) ; DOI  [10.1073/pnas.1312701111](publications/search?query=10.1073%2Fpnas.1312701111)
* **Terms.** Example: [hypothalamus](terms/search?query=hypothalamus)

To switch between sections, simply toggle between "Proteins", "Publications" and "Terms". Note that unless you clear the query box, your last query is kept in the search field. 

**Asterisks** can be used at the beginning and within terms. Note that terms starting with an asterisk or a single letter followed by an asterisk can slow down queries considerably.

_Example_: [insulin*](proteins/search?query=insulin*) returns all entries containg terms starting with "insulin" (i.e. insulin, Insulinemia, etc.). 

If you enter **multiple terms**, the AND operator is applied by default.

_Example_: Searching for [Adrenocortical carcinoma](proteins/search?query=Adrenocortical%20carcinoma) and [Adrenocortical and carcinoma](proteins/search?query=Adrenocortical%20and%20carcinoma) return all entries containing both terms.

Searching for multiple terms enclosed in **quotes** returns all entries containing both terms in the exact order (exact term string).

_Example_: ["Adrenocortical carcinoma"](proteins/search?query=%22Adrenocortical%20carcinoma%22)

Searching in publications returns all publications containing the term(s) in either the citation data or abstract. By using **prefixes** in the search, the search can be restricted to one of the following fields:

* **title** Example: [title:prion](publications/search?query=title:prion)
* **abstract** Example: [abstract:BRCA1](publications/search?query=abstract:BRCA1)
* **author** Example: [author:Doolittle](publications/search?query=author:Doolittle)
* **journal** Example: [journal:plos biology](publications/search?query=journal:plos%20biology)
* **volume** Example: [volume:51](publications/search?query=volume:51)
* **year** Example: [year:2007](publications/search?query=year:2007)

Searching for multiple terms containing prefixes returns all publications matching both constraints.

_Example_: Searching in publications for  [author:Doolittle year:2007](publications/search?query=author:Doolittle%20year:2007) returns all publications published by Doolittle in 2007.

**By default, only Gold quality data is searched.** To find entries with both Gold and Silver data matching the query, select "Include silver" in the drop down menu in front of the search box. Please note that the concept of Gold/Silver quality data only applies to the search in "Proteins".

_Example_: Compare the results of searching for the Gene Ontology term  "Exocrine pancreas development" [GO:0031017 Gold only](proteins/search?query=GO:0031017) and [GO:0031017 Include silver](proteins/search?query=GO:0031017&quality=gold-and-silver).
