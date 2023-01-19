## New functionality of the feature viewer

Users can now download a .svg image of the positional features they are exploring.

## Improved traceability of function predictions

All our function predictions are associated with ECO terms reflecting the type of data analysis that was performed. 
In some cases, the analysis was not done with human data but with data from model organisms. This is now clearly specified.

Example: [TMEM 53 predictions](../entry/NX_Q6P2H8/function-predictions)

All entries with function predictions are listed [here](../proteins/search?listId=9O74XY11).

## New SPARQL query

The query **NXQ_00300** available on [the SNORQL interface](https://snorql.nextprot.org/) retrieves all human proteins with protein existence "At protein level" (PE=1) 
that have no function annotated, are highly expressed in brain and have homologs in <i>Drosophila melanogaster</i> according to [OrthoDB](https://www.orthodb.org/). <br> 
