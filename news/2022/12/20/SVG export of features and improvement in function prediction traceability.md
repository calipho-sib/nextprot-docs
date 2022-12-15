##SVG export of positional features

The graphical interface of the feature viewer has been improved so that users can download a .svg image of the positional features they are exploring.

##Improved traceability of function predictions

All our function predictions are associated with ECO terms reflecting the type of data analysis that was performed. 
In some cases, this analysis is not done with human data but with data obtained in model organisms. This is now specified in the predictions.

Example: [TMEM 53 predictions](../entry/NX_Q6P2H8/function-predictions)

##New SPARQL query

The query **NXQ_00300** available on [the SNORQL interface] (https://snorql.nextprot.org/), retrieves all human proteins with protein existence "At protein level" (PE=1) 
that have no function annotated, are highly expressed in brain and have homologs in Drosophila melanogaster according to OrthoDB. 
It is federated with [OrthoDB] (https://www.orthodb.org/) :<br> 


