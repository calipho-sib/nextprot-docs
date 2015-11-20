#Developer API

The [REST api](https://api.nextprot.org) and the [SPARQL endpoint](https://api.nextprot.org/sparql) can be freely used by anyone (we simply ask you to reference us somehow). 

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

Getting the overview of a protein is as simple as: (see it in live in this [jsfiddle](http://jsfiddle.net/ddtxra/Lqkmuzm3/)) 
```javascript

  nx.getProteinOverview('NX_P01308').then(function(overview){
    console.log(overview);
  });  
  
```

Or getting the sequence of the isoforms (see it in live in this [jsfiddle](http://jsfiddle.net/ddtxra/9Lt6n8jb/3/))
```javascript

  nx.getProteinSequence('NX_P01308').then(function(sequence){
    console.log(sequence[0]); //Gets sequence of the 1st isoform
  });  
  
```

Or you can easily visualize sequence features with our [feature viewer](https://github.com/calipho-sib/feature-viewer): See it in live in [jsfiddle](http://jsfiddle.net/ddtxra/fm51dwz7/4/)

###SPARQL example 
For executing a sparql, simply use nx.executeSparql:

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
See an example of protein existence in live in [bl.ocks.org](http://bl.ocks.org/ddtxra/a1fd0e5613ed6b72ff8f) or edit it in [jsfiddle](http://jsfiddle.net/ddtxra/x3umjp67/) (supports: chrome, firefox or safari, microsoft edge).

<a href="http://bl.ocks.org/ddtxra/a1fd0e5613ed6b72ff8f" target="_blank"> <img width="25%" src="https://raw.githubusercontent.com/calipho-sib/nextprot-docs/master/help/assets/pie-protein-chart-existence.png"/>
</a>

#Node, npm and BioJS
We have also published an npm module and registered it in BIOJS.net: http://biojs.io/d/biojs-rest-nextprot

To make use of the module simply type on your shell ```npm install biojs-rest-nextprot``` (requires node and npm)

To retrieve the sequence of the isoforms of an entry, create a file (ex: print-sequence.js):
```
var nextprot = require("biojs-rest-nextprot");
nextprot.getProteinBlock('NX_P01308', 'isoform', function (data) {
   data.entry.isoforms.map(function (i) {
       console.log(i.sequence)
   })
});
```
Run "node print-sequence.js” and that’s it! You should get in your console the sequence of the insulin (NX_P01308):
```
	MALWMRLLPLLALLALWGPDPAAAFVNQHLCGSHLVEALYLVCGERGFFYTPKTRREAEDLQVGQVELGGGPGAGSLQPLALEGSLQKRGIVEQCCTSICSLYQLENYCN
```

#Develop and contribute

You can create viewers that integrates very easily in our platform putting them on [GitHub](https://www.github.com/).

The following URL will match the GitHub repositry for the given user:

https://search.nextprot.org/entry/{entryAccession}/gh/{githubUser}/{githubRepositry}

* Please note that the branch should be named gh-pages and an index.html should be in the root folder

Look at a real example now:
https://search.nextprot.org/entry/NX_P01308/gh/ddtxra/protein-existence-levels

To start with, you can fork the sources of the real example on GitHub: [https://github.com/ddtxra/protein-existence-levels](https://github.com/ddtxra/protein-existence-levels). Instruction on how to publish in nextprot website are part of the readme file.

Happy programming! 

If you need some help, don't hesitate to [contact us](mailto:support@nextprot.org). One of our developer will be more than happy to assist you.

## Other viewers

* [sparql - Genes per chromosome](http://bl.ocks.org/ddtxra/4a5189dba66cd84aefd1)

More complex viewers can be seen in our [github](https://github.com/calipho-sib/nextprot-viewers) repository (will be soon integrated):

* [Annotation Statistics](https://cdn.rawgit.com/calipho-sib/nextprot-viewers/master/annot-stats/app/assets/index.html)
* [Peptide Viewer with entry passed as parameter](https://cdn.rawgit.com/calipho-sib/nextprot-viewers/master/peptide-viewer/app/assets/index.html?nxentry=NX_P46976)

