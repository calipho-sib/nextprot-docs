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

#Node

To make use of the module simply type on your shell ```npm install nextprot-cli``` (requires node and npm)

To retrieve the sequence of the isoforms of an entry, create a file (ex: print-sequence.js):
```
var NextProtClient = require("nextprot-cli");
var nx = new NextProtClient("test applicaton", "student at UNIGE");

nx.getProteinBlock('NX_P01308', 'isoform', function (data) {
   data.entry.isoforms.map(function (i) {
       console.log(i.sequence)
   })
});
```
Run "node print-sequence.js” and that’s it! You should get in your console the sequence of the insulin (NX_P01308):
```
	MALWMRLLPLLALLALWGPDPAAAFVNQHLCGSHLVEALYLVCGERGFFYTPKTRREAEDLQVGQVELGGGPGAGSLQPLALEGSLQKRGIVEQCCTSICSLYQLENYCN
```

#BioJS
We have registered 3 modules on BioJS that we use to build our views. 

* Sequence Viewer (independent of neXtProt): [http://biojs.io/d/sequence-viewer](http://biojs.io/d/sequence-viewer)
* Feature Viewer (independent of neXtProt): [http://biojs.io/d/feature-viewer](http://biojs.io/d/feature-viewer)
* nextprot-cli: [http://biojs.io/d/nextprot-cli](http://biojs.io/d/nextprot-cli)

We are glad to share those modules with you and if you are interested to collaborate on one of them let us know.

#Develop and contribute

You can create viewers that integrates very easily in our platform putting them on GitHub. You have 2 options:

* [Gist](https://gist.github.com/): If you add your index.htlm in gist, you can use neXtProt with  the following url:
https://search.nextprot.org/entry/{entryAccession}/gist/{githubUser}/{gistId}
for example:
[https://search.nextprot.org/entry/NX_P01308/gist/ddtxra/a3a860b6d0c0e1ab0f76](https://search.nextprot.org/entry/NX_P01308/gist/ddtxra/a3a860b6d0c0e1ab0f76) corresponds to this gist: [http://bl.ocks.org/ddtxra/a3a860b6d0c0e1ab0f76](http://bl.ocks.org/ddtxra/a3a860b6d0c0e1ab0f76).

* [Github repo](https://github.com/): (this will be soon documented!)

If you develop a viewer and would like to integrate it in neXtProt interface, you can simply [edit this file](https://github.com/calipho-sib/nextprot-viewers/edit/master/community/community-entry-viewers.json) and create a pull request or [let us know](mailto:support@nextprot.org) by email.

To start with, you can fork an existing [gist](https://gist.github.com/ddtxra/a3a860b6d0c0e1ab0f76).

Note that the entry is pass as an http parameter `nxentry`. Check for instance these 2 urls [pirin](http://bl.ocks.org/ddtxra/raw/a3a860b6d0c0e1ab0f76/?nxentry=NX_O00625) and 
[titin](http://bl.ocks.org/ddtxra/raw/a3a860b6d0c0e1ab0f76/?nxentry=NX_Q8WZ42)


Happy programming! 

If you need some help, don't hesitate to [contact us](mailto:support@nextprot.org). One of our developer will be more than happy to assist you.

## Other viewers

* [sparql - Genes per chromosome](http://bl.ocks.org/ddtxra/4a5189dba66cd84aefd1)

More complex viewers can be seen in our [github](https://github.com/calipho-sib/nextprot-viewers) repository:

* [Annotation Statistics](https://cdn.rawgit.com/calipho-sib/nextprot-viewers/master/statistics/annotations/app/index.html)
* [Peptide viewer with entry passed as parameter](https://cdn.rawgit.com/calipho-sib/nextprot-viewers/master/peptides/app/index.html?nxentry=NX_P46976)

