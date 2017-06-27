##Federated queries are now supported

A federated SPARQL query allows a user to search multiple databases in parallel in real time, take the results and present them in the desired form. Examples are found in our [Snorql interface](https://snorql.nextprot.org/) with the tag &#34;federated query&#34;. The neXtProt data set can now be accessed online via a SPARQL federated query. Both GET and POST methods are supported. Documentation and examples are provided at [https://api.nextprot.org/sparql](https://api.nextprot.org/sparql).

##Chromosome reports

The chromosome report files list all the entries mapped to the chromosome, as well as basic information concerning each entry. In addition to being downloadable from our FTP site, these are now provided via our [web](https://www.nextprot.org/entries/all-chromosomes) and [API](https://api.nextprot.org/).

The following improvements have been made:

1. The data in the columns are now aligned making it easier to import the data in Excel.
2. Coding strand information has been added.
3. Values in the "Antibody" column have been corrected for a small number of entries.
