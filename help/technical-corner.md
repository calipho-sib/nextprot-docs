The technical corner is dedicated to developers willing to get data programmatically or use our viewer libraries.

* Viewer libraries
* Programmatic access (JSON, XML using our REST API). SPARQL endpoint 

<h1><a id="viewers"/>Viewers</h1><!-- used like this because of the anchor -->

Our viewers are javascript components that can freely be re-used under the GNU General Public License as published by the Free Software Foundation; either version 2 of the License, or (at your option) any later version.

The code source and examples can be found on [GitHub Calipho SIB repository](www.github.com/calipho-sib) and also on [BioJS registry](http://www.biojs.io/).

###Feature viewer

A javascript tool based on the library D3, will allow you to display the features covering your sequence of DNA, protein, or others.

<a href="https://cdn.rawgit.com/calipho-sib/feature-viewer/v0.1.40/examples/index.html" target="_blank"> <img src="https://cdn.rawgit.com/calipho-sib/nextprot-docs/develop/help/assets/feature-viewer.png"/></a>

###Sequence viewer

This javascript tool will allows to display sequences of DNA, protein, or others, formatted FASTA-like, and apply some visual improvment for selection and coverage

<a href="https://cdn.rawgit.com/calipho-sib/sequence-viewer/master/examples/index.html" target="_blank"> <img src="https://cdn.rawgit.com/calipho-sib/nextprot-docs/develop/help/assets/sequence-viewer.png"/></a>


###Hierarchical Heatmap Table 

This javascript component will allow to display hierarchical tables with custom templates.

<a href="https://cdn.rawgit.com/calipho-sib/hierarchic-heatmap-table-component/master/doc/index.html" target="_blank"> <img src="https://cdn.rawgit.com/calipho-sib/nextprot-docs/develop/help/assets/hierarchical-heatmap-table.png"/></a>


<h1><a id="programmatic-access"/>Programmatic Access</h1><!-- used like this because of the anchor -->

The [REST api](https://api.nextprot.org) and the [SPARQL endpoint](https://api.nextprot.org/sparql) can be freely used by anyone.

You can get the content of an entry in different format by using the api like this:

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

For the ease of development in javascript we have built a [library](https://github.com/calipho-sib/nextprot-js) that wraps the API and SPARQL endpoint. You just need to initialize with some information about what your application is doing and who you are.

```javascript

  var applicationInfo = "demo app to get the overview"; //provide us with some information about what your app is doing
  var clientInfo = "calipho group at SIB"; //provide us with some information about who you are
  var nx = new Nextprot.Client(applicationInfo, clientInfo);

```

###API example

Getting the overview of a protein is as simple as: (see it in live in this [jsfiddle](http://jsfiddle.net/ddtxra/Lqkmuzm3/)\)

```javascript

  nx.getProteinOverview('NX_P01308').then(function(overview){
    console.log(overview);
  });  

```

Or getting the sequence of the isoforms (see it in live in this [jsfiddle](http://jsfiddle.net/ddtxra/9Lt6n8jb/3/)\)

```javascript

  nx.getProteinSequence('NX_P01308').then(function(sequence){
    console.log(sequence[0]); //Gets sequence of the 1st isoform
  });  

```

Or you can easily visualize sequence features with our [feature viewer](https://github.com/calipho-sib/feature-viewer): See it in live in [jsfiddle](http://jsfiddle.net/ddtxra/fm51dwz7/4/)

###SPARQL example For executing a sparql, simply use nx.executeSparql:

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


##Develop and contribute

You can create community viewers that integrates very easily on neXtProt platform by sharing your code on [GitHub](https://www.github.com/).

The following URL will match the GitHub repository for the given user:

https://www.nextprot.org/entry/{entryAccession}/gh/{githubUser}/{githubRepository\}

-	Please note that the branch should be named gh-pages and an index.html should be in the root folder. The information about the entry will be passed as a parameter.

Look at a real example now: https://www.nextprot.org/entry/NX_Q01101/gh/Alain-Gateau/Protein-3D-structure

To start with, you can fork the sources of this real example on GitHub: [https://github.com/ddtxra/Protein-3D-structure](https://github.com/ddtxra/Protein-3D-structure). 

If you need some help, don't hesitate to [contact us](mailto:support@nextprot.org). One of our developer will be more than happy to assist you.



##Snippets and demo examples  

-	[sparql - Genes per chromosome](http://bl.ocks.org/ddtxra/4a5189dba66cd84aefd1)

See an example of protein existence in live in [bl.ocks.org](http://bl.ocks.org/ddtxra/a1fd0e5613ed6b72ff8f) or edit it in [jsfiddle](http://jsfiddle.net/ddtxra/x3umjp67/) (supports: chrome, firefox or safari, microsoft edge).

<a href="http://bl.ocks.org/ddtxra/a1fd0e5613ed6b72ff8f" target="_blank"> <img width="25%" src="https://raw.githubusercontent.com/calipho-sib/nextprot-docs/master/help/assets/pie-protein-chart-existence.png"/></a>
