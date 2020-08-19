The technical corner is dedicated to developers wanting to get our data programmatically or to use our viewer libraries.

* [Programmatic access](#programmatic-access) (JSON, XML using our REST API; SPARQL endpoint)
* [Viewer libraries](#viewers)

<h1><a id="programmatic-access"/>Programmatic Access</h1><!-- used like this because of the anchor -->

The [REST API](https://api.nextprot.org) and the [SPARQL endpoint](https://api.nextprot.org/sparql) can be freely used by all.

You can get the content of an entry in a variety of formats by using the API like this:

```
https://api.nextprot.org/entry/NX_P01308.xml //Gets the entry in xml
https://api.nextprot.org/entry/NX_P01308.json //Gets the entry in JSON
https://api.nextprot.org/entry/NX_P01308.ttl //Gets the entry in TURTLE

https://api.nextprot.org/entry/NX_P01308/overview.xml //Gets only the overview in xml
https://api.nextprot.org/entry/NX_P01308/overview.json //Gets only the overview in JSON
https://api.nextprot.org/entry/NX_P01308/overview.ttl //Gets only the overview in TURTLE

https://api.nextprot.org/entry/NX_P01308/secondary-structure.xml //Gets only the secondary structure (helix, turn, beta-strand) in XML
https://api.nextprot.org/entry/NX_P01308/secondary-structure.json //Gets only the secondary structure (helix, turn, beta-strand) in JSON

https://api.nextprot.org/entry/NX_P01308/helix.xml //Gets only the helix annotations in XML
https://api.nextprot.org/entry/NX_P01308/helix.json //Gets only the helix annotations in JSON
```

For ease of development in javascript, we have built a [library](https://github.com/calipho-sib/nextprot-js) that wraps the API and SPARQL endpoint. You just need to initialize it with some information about what your application does and who you are.

```javascript

  var applicationInfo = "demo app to get the overview"; //provide us with some information about what your app is doing
  var clientInfo = "calipho group at SIB"; //provide us with some information about who you are
  var nx = new Nextprot.Client(applicationInfo, clientInfo);

```

### API example : Javascript neXtProt client library

Getting the overview of a protein is as simple as: (see it live in this [jsfiddle](https://jsfiddle.net/matschaeff/5wdg7qv1/9/)\)

```javascript

  nx.getProteinOverview('NX_P01308').then(function(overview){
    console.log(overview);
  });  

```

Or getting the sequence of the isoforms for an entry (see it live in this [jsfiddle](http://jsfiddle.net/matschaeff/qj8zb9u7/10/)\)

```javascript

  nx.getProteinSequence('NX_P01308').then(function(sequence){
    console.log(sequence[0]); //Gets sequence of the 1st isoform
  });  

```

### API example : Python 2

Getting the overview of a protein, using a python HTTP client library and JSON library

```python
  import http.client
  import json

  conn = http.client.HTTPSConnection("api.nextprot.org")
  conn.request("GET", "/entry/NX_P01308")
  res = conn.getresponse()

  entry_data = res.read()
  entry_json = json.loads(entry_data)
  overview = entry_json["entry"]["overview"]

  print(json.dumps(overview, indent=4, sort_keys=True))
```


### SPARQL example 

To execute a SPARQL query, simply use nx.executeSparql:

```javascript
var sparqlQuery ='SELECT ?pe count(?entry) as ?cnt WHERE {?entry :existence ?pe} group by ?pe';
//execute sparql and retrieve result
nx.executeSparql(sparqlQuery).then(function (result){
  var seriesData = [];
    result.results.bindings.map(function (data) {
      seriesData.push([data.pe.value, parseInt(data.cnt.value)]); //gets number of entries
    });
    console.log(seriesData);
});
```


## Develop and contribute

You can create a community viewer that integrates very easily in the neXtProt platform by sharing your code on [GitHub](https://www.github.com/).

The following URL will match the GitHub repository for a given user:

https://www.nextprot.org/entry/{entryAccession}/gh/{githubUser}/{githubRepository\}

-	Please note that the branch should be named gh-pages and an index.html should be found in the root folder. The information about the entry will be passed as a parameter.

Look at this real example: https://www.nextprot.org/entry/NX_Q01101/gh/Alain-Gateau/Protein-3D-structure

To start with, you can fork the sources of this real example on GitHub: [https://github.com/ddtxra/Protein-3D-structure](https://github.com/ddtxra/Protein-3D-structure). 

If you need some help, don't hesitate to [contact us](mailto:support@nextprot.org). One of our developers will be more than happy to assist you.



## Snippets and demo examples  

-	[SPARQL - Genes per chromosome](http://bl.ocks.org/ddtxra/4a5189dba66cd84aefd1)

View an example of protein existence live in [bl.ocks.org](http://bl.ocks.org/ddtxra/a1fd0e5613ed6b72ff8f) or edit it in [jsfiddle](http://jsfiddle.net/matschaeff/0preyjw7/8/) (supports: chrome, firefox or safari, microsoft edge).

<a href="http://bl.ocks.org/ddtxra/a1fd0e5613ed6b72ff8f" target="_blank"> <img width="25%" src="https://raw.githubusercontent.com/calipho-sib/nextprot-docs/master/help/assets/pie-protein-chart-existence.png"/></a>



<h1><a id="viewers"/>Viewers</h1><!-- used like this because of the anchor -->

Our viewers are javascript components that can be freely re-used under the GNU General Public License as published by the Free Software Foundation (either version 2 or greater of the License).

The source code and examples are found in the [GitHub Calipho SIB repository](http://www.github.com/calipho-sib) and in [BioJS registry](https://biojs.net/?#/search/nextprot).

### Feature viewer

A javascript tool, based on the library D3, which allows you to display features mapping to your sequence (DNA, protein, or other).

<a href="https://cdn.rawgit.com/calipho-sib/feature-viewer/v0.1.40/examples/index.html" target="_blank"> <img src="https://cdn.rawgit.com/calipho-sib/nextprot-docs/develop/help/assets/feature-viewer.png"/></a>

**Reference**

Paladin L, Schaeffer M, Gaudet P, Zahn-Zabal M, Michel PA, Piovesan D, Tosatto SCE, Bairoch A. **The Feature Viewer: A visualization tool for positional annotations on a sequence.** Bioinformatics. 2020 Jan 27. pii: btaa055. [doi: 10.1093/bioinformatics/btaa055](http://dx.doi.org/10.1093/bioinformatics/btaa055).

### Sequence viewer

This javascript tool allows you to display a sequence (DNA, protein, or other) in a FASTA-like formatted and to apply some visual improvements for selection and coverage.

<a href="https://cdn.rawgit.com/calipho-sib/sequence-viewer/master/examples/index.html" target="_blank"> <img src="https://cdn.rawgit.com/calipho-sib/nextprot-docs/develop/help/assets/sequence-viewer.png"/></a>


### Hierarchical Heatmap Table 

This javascript component allows hierarchical tables to be displayed using custom templates.

<a href="https://cdn.rawgit.com/calipho-sib/hierarchic-heatmap-table-component/master/doc/index.html" target="_blank"> <img src="https://cdn.rawgit.com/calipho-sib/nextprot-docs/develop/help/assets/hierarchical-heatmap-table.png"/></a>
