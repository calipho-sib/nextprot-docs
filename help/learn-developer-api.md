#Developer API

The [REST api](https://api.nextprot.org) and the [SPARQL endpoint](https://api.nextprot.org/sparql) can be freely used by anyone. 

We have built a javascript [library](https://github.com/calipho-sib/nextprot-js) that wraps the API and SPARQL endpoint. 

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

Note that you can use the API or the SPARQL endpoint directly with any other language.

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
