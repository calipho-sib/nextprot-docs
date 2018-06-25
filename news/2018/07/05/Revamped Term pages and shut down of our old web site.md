Controlled vocabularies provide a way to organize knowledge for subsequent retrieval. neXtProt uses a number of controlled vocabularies to describe concepts such as protein families, domains, molecular function and subcellular locations.

##Term page changes

The term page provides information about the term. The PROSITE or INTERPRO documentation for protein domains is now accessible via a link in the EXTERNAL REFERENCES section. The ATOMIC CORRECTION FORMULA for post-translational modifications (PTMs) is displayed more explicitly such that it adds up to the average mass difference. Entries relevant to the term displayed and all its children are displayed. The new "Include silver" option allows entries with relevant silver data to be included.

##Ancestor graph changes

The "Ancestor graph" has been renamed "Relationship graph" to underline that it displays relationships other than parent-child between terms. The direction and type of relationship between two terms is now explicitly displayed. The following examples illustrate the various relationships:

*	**Anatomy:** Abdomen [TS-0001](../term/ TS-0001/relationship-graph) (is a, part of)
*	**Cell line:** PC-3M-LN2 [CVCL_L156](../term/CVCL_L156/relationship-graph) (derives from)
*	**Biological process:** Negative regulation of DNA recombination [GO:0045910](../term/ GO:0045910/relationship-graph) (negatively regulates, regulates)
*	**Biological process:** Positive regulation of cell motility [GO:2000147](../term/ GO:2000147 /relationship-graph) (positively regulates)

##Tree browser changes

The tree browser displays the different paths from the controlled vocabulary root term to the term displayed. For all the terms displayed, the children can be displayed or hidden. Entries with silver confidence level data are counted in the number of relevant entries when the "Include silver" option is selected.

##Deprecation of our old web site and API

Having completed the revamping of our web site, we will disconnect our original website [http://old.nextprot.org](http://old.nextprot.org) and the associated API [http://old.nextprot.org/rest/](http://old.nextprot.org/rest/) in a month. Users should switch to using our website at [https://www.nextprot.org/](https://www.nextprot.org/) and scripts modified to call our API at [https://api.nextprot.org/](https://api.nextprot.org/).

Please do not hesitate to contact us if you need help.
