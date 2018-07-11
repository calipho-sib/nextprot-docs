Controlled vocabularies provide a way to organize knowledge for subsequent retrieval. neXtProt uses a number of controlled vocabularies to describe concepts such as protein families, domains, molecular function and subcellular locations.

##Term page changes

The term page provides information about the term. The PROSITE or INTERPRO documentation for protein domains is now accessible via a link in the EXTERNAL REFERENCES section. The ATOMIC CORRECTION FORMULA for post-translational modifications (PTMs) is displayed more explicitly such that it adds up to the average mass difference.

**Changes to Proteins**

Entries relevant to the term displayed and all its children are displayed. The new "Include silver" option allows entries with relevant silver data to be included.

**Changes to Ancestor graph**

The "Ancestor graph" has been renamed "Relationship graph" to underline that it displays relationships other than parent-child between terms. The direction and type of relationship between two terms is now explicitly displayed.

Examples:

*	Graph showing relationships _is a_ and _part of_: Abdomen [TS-0001](../term/TS-0001/relationship-graph)
*	Graph showing relationship _derives from_: #40a [CVCL_IW91](../term/CVCL_IW91/relationship-graph)
*	Graph showing relationships _is a_, _negatively regulates_ and _regulates_: Negative regulation of DNA recombination [GO:0045910](../term/GO:0045910/relationship-graph)
*	Graph showing relationships _is a_, _part of_, _positively regulates_ and _regulates_: Positive regulation of cell motility [GO:2000147](../term/GO:2000147/relationship-graph)

**Changes to Tree browser**

The tree browser displays the different paths from the controlled vocabulary root term to the term displayed. For all the terms displayed, the children can be displayed or hidden. Entries with silver confidence level data are counted in the number of relevant entries when the "Include silver" option is selected.

##Deprecation of our old web site and API

Having completed the revamping of our web site, we will disconnect our original website [http://old.nextprot.org](http://old.nextprot.org) and the associated API [http://old.nextprot.org/rest/](http://old.nextprot.org/rest/) in a month. Users should switch to using our website at [https://www.nextprot.org/](https://www.nextprot.org/) and scripts modified to call our API at [https://api.nextprot.org/](https://api.nextprot.org/).

Please do not hesitate to contact us if you need help.

##Modified advanced search SPARQL queries

Queries involving subcellular localization have been reviewed and modified (NXQ\_00001, NXQ\_00002, NXQ\_00005, NXQ\_00010, NXQ\_00016, NXQ\_00017, NXQ\_00018, NXQ\_00021, NXQ\_00023, NXQ\_00026, NXQ\_00035, NXQ\_00042, NXQ\_00057, NXQ\_00066, NXQ\_00070, NXQ\_00076, NXQ\_00078, NXQ\_00081, NXQ\_00099, NXQ\_00130, NXQ\_00218). Note that in most cases the queries have been modified to take into account that GO cellular component terms can have an equivalent UniProtKB subcellular location and vice-versa.
