The advent of robust open-source search engines based on RDF and SPARQL query langage, such as virtuoso, allowed us to design this new efficient search system, enabling fine-grained semantically-oriented queries and incorporating many features and constraints not available in classical (Lucene-based) query systems.

With SPARQL the subjects and objects matched with a constraint become available variables ready to match the next constraints, allowing chaining and implementing the OR, AND, NOT of classical searches. The objects of queries and the results returned can be of any type, entries, isoforms, sites, domains, diseases, tissues, peptides, locations...

Opening the sequence space:
Traditional protein databases don't allow queries combining sequence with other criteria. Sequences are exposed only to blast or predefined pattern/profile matches (PROSITE, Pfam), therefore querying both sequence and annotations is a multistep operation, often necessitating a bioinformatician that would download partial results and script on the data. Hence offering authentic realtime sequence searches with full regex capabilities allows one-step targeted queries not available elsewhere.

Domain architecture searches:
Proteins with 1 to x domains D1 followed (preceeded) by 1 to y domains D2

Potential PTM switch or cross-talk: proteins with distinct PTMs at adjacent sites

Indirections and inference:
The cascading of graph operations and filters allow indirect requests unreachable with other search engines. For example, proteins P that interact with substrates of kinase K, or proteins P that interact with a member of family F,
or proteins P that interact with at least x proteins containing a domain D.

We are in the process of buiding a suite of javascript-based widgets allowing appropriate grephical repersentations
for the query results.

