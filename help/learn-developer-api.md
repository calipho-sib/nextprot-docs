#Developer API

The [REST api](https://api.nextprot.org) and the [SPARQL endpoint](https://api.nextprot.org/sparql) can be freely used by anyone (we just ask you to reference us). 

You can get the content of an entry in different format by using the api like this:
```
https://api.nextprot.org/entry/NX_P01308.xml //Gets the entry in xml
https://api.nextprot.org/entry/NX_P01308/overview.xml //Gets only the overview
https://api.nextprot.org/entry/NX_P01308/secondary-structure.xml //Gets only the secondary structure (helix, turn, beta-strand)
```

For web development, you can ask for the same urls finishing with json extension instead of xml. (we will provide other formats soon)

For the ease of development in javascript we have built [library](https://github.com/calipho-sib/nextprot-js) that wraps the API and SPARQL endpoint. 

With this library getting the overview of a protein is as simple as: 
```javascript

  var applicationInfo = "demo app to get the overview"; //provide us with some information about what your app is doing
  var clientInfo = "calipho group at SIB"; //provide us with some information about who you are
  var nx = new Nextprot.Client(applicationInfo, clientInfo);

  nx.getProteinOverview('NX_P01308').then(
    function(overview){
    console.log(overview);
  });  
  
```

or for executing a sparql, simply use nx.executeSparql:

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
<img width="75%" src="https://raw.githubusercontent.com/calipho-sib/nextprot-docs/master/help/assets/pie-protein-chart-existence.png"/>

See it in action here (supports: chrome, firefox or safari): (http://bl.ocks.org/ddtxra/a1fd0e5613ed6b72ff8f)

##REST API viewers examples
* [Example 1 - Protein Secondary Structure](http://bl.ocks.org/ddtxra/75545ffaa0c6db260a40)
* [Example 2 - Protein Secondary Structure with another entry passed as url parameter ](http://bl.ocks.org/ddtxra/raw/75545ffaa0c6db260a40/?nxentry=NX_Q96EY8)

##SPARQL viewers examples

* [Example 1 - Protein Existence](http://bl.ocks.org/ddtxra/a1fd0e5613ed6b72ff8f)
* [Example 2 - Genes per chromosome](http://bl.ocks.org/ddtxra/4a5189dba66cd84aefd1)


##neXtProt viewers (soon integrated)
More complex viewers can be seen in our [github](https://github.com/calipho-sib/nextprot-viewers) repository:

* [Annotation Statistics](https://cdn.rawgit.com/calipho-sib/nextprot-viewers/master/annot-stats/app/assets/index.html)
* [Peptide Viewer with entry passed as parameter](https://cdn.rawgit.com/calipho-sib/nextprot-viewers/master/peptide-viewer/app/assets/index.html?nxentry=NX_P46976)
