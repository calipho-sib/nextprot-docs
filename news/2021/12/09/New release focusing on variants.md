This release, neXtProt data release 2021-MM-DD, incorporates new variants causing disease from neXtProt, as well as variants found in cell lines from the Cellosaurus.

##Changes to the data

**New variants relevant to Rett syndrome**

Rett syndrome is an X-linked dominant neurodevelopmental disorder that is generally caused by a genetic variation in [MECP2](../entry/NX_P51608/medical). A total of 240 MECP2 variants were integrated from the paper by [Ehrhart et al. (2021)](https://doi.org/10.1038/s41597-020-00794-7). Of these, 183 cause Rett syndrome whereas 57 variants do not.

**New variants from the Cellosaurus**

The [Cellosaurus](https://web.expasy.org/cellosaurus/), a knowledge resource on cell lines, provides information on important sequence variations (compared to the reference genome of the species). A total of ? variants from the Cellosaurus are now found in neXtProt. Example: Variant ? at position ? in [](../entry/NX_/sequence).

**HGVS nomenclature**

The [Human Genome Variation Society](https://varnomen.hgvs.org/) (HGVS) nomenclature for all non-synonymous single amino acid variants (SAAVs) is now displayed. Example: Variant A -> V at position 20 in MSH6 isoform GTBP-N is displayed as p.Ala20Val in the [Medical](../entry/NX_P52701/medical), [Sequence view](../entry/NX_P52701/sequence) and [Structures view](../entry/NX_P52701/structures).

It is now also possible to search for HGVS variant names. Example: Searching in proteins for [p.Ala20Val](../proteins/search?query=p.Ala20Val) returns MSH6.

##Updated data

UniProt release 2021_02 and Ensembl release 102 have been integrated. GO annotations from GOA have also been updated and now have a qualifier associated. The data from GlyConnect has also been updated.

##New keyword

The neXtProt keyword _Rare disease_ (KW-2001) tags all entries with an Orphanet cross-reference to a rare disease. This new keyword allows all entries associated with a rare disease to be retrieved - see [KW-2001](../term/KW-2001).

##New cross-reference

Cross-references to DECIPHER, a web-based resource and database of genomic variation data from analysis of patient DNA, have been added to the Medical view. Example: [SCN1A](../entry/NX_P35498/medical).

##Changes to the RDF data model

The disease-causing variants annotated by neXtProt have required the new entity ????

##Changes to the export files

The genome assembly is now included in the header of all ? files, as well as the ttl file.
