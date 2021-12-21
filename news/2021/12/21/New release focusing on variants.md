This last release of the year, neXtProt data release 2021-11-19, incorporates new variants causing disease from neXtProt, as well as variants found in cell lines from the Cellosaurus.

##Changes to the data

**New variants relevant to Rett syndrome**

Rett syndrome is an X-linked dominant neurodevelopmental disorder that is generally caused by a genetic variation in [MECP2](../entry/NX_P51608/medical). A total of 240 MECP2 variants were integrated from the paper by [Ehrhart et al. (2021)](https://doi.org/10.1038/s41597-020-00794-7). Of these, 183 cause Rett syndrome whereas 57 variants do not.

**New variants from the Cellosaurus**

The [Cellosaurus](https://web.expasy.org/cellosaurus/), a knowledge resource on cell lines, provides information on important sequence variations (compared to the reference genome of the species). A total of 2470 variants from the Cellosaurus are now found in neXtProt. Example: Variant Q -> P (p.Gln65Pro) at position 65 in serine-protein kinase ATM [NX\_Q13315](../entry/NX_Q13315/sequence).

**HGVS nomenclature**

The [Human Genome Variation Society](https://varnomen.hgvs.org/) (HGVS) nomenclature for all non-synonymous single amino acid variants (SAAVs) is now displayed. Example: Variant A -> V at position 20 in MSH6 isoform GTBP-N is displayed as p.Ala20Val in the [Medical](../entry/NX_P52701/medical), [Sequence](../entry/NX_P52701/sequence) and [Structures](../entry/NX_P52701/structures) views.

It is now also possible to search for HGVS variant names. Example: Searching in proteins for [p.Ala20Val](../proteins/search?query=p.Ala20Val) returns MSH6.

##Updated data

UniProt release 2021_02 and Ensembl release 102 have been integrated. GO annotations from GOA have also been updated and now have a qualifier associated. The data from GlyConnect has also been updated.

##New keyword

The neXtProt keyword _Rare disease_ (KW-2001) tags all entries with an Orphanet cross-reference to a rare disease. This new keyword allows all entries associated with a rare disease to be retrieved - see [KW-2001](../term/KW-2001).

##New cross-reference

Cross-references to DECIPHER, a web-based resource and database of genomic variation data from analysis of patient DNA, have been added to the Medical view. Example: [SCN1A](../entry/NX_P35498/medical).

##Changes to the RDF data model

Disease-related variants in neXtProt are described by the new entity :diseaseRelatedVariant. Disease(s) associated with protein defect(s) can now be described using NCI Thesaurus (:NciThesaurusCv) controlled vocabulary terms.

##Changes to advanced search SPARQL queries

The following queries have been modified to take into account the changes in the data model:
1. [NXQ\_00028](../proteins/search?mode=advanced&queryId=NXQ_00028) **Proteins associated with a disease but without a disease-causing amino-acid substitution variant**
2. [NXQ\_00048](../proteins/search?mode=advanced&queryId=NXQ_00048) **Proteins with at least one variant of the type "C->X" (Cys to anything else) that are linked to one or more diseases**
3. [NXQ\_00082](../proteins/search?mode=advanced&queryId=NXQ_00082) **Proteins whose genes are on chromosome 21 that have "gold" variants not associated with a disease**

##Changes to the export files

The genome assembly is now included in all ttl files starting with nextprot\_chromosome\_ at [https://download.nextprot.org/pub/current\_release/rdf/ttl/](https://download.nextprot.org/pub/current_release/rdf/ttl/). It is now also found in the header line of all mapping files in [https://download.nextprot.org/pub/current\_release/mapping/](https://download.nextprot.org/pub/current_release/mapping/).

A user spotted that our ttl files contained literals containing backslashes. These form invalid escape sequences and are ignored by virtuoso when loading data. These literals have now been fixed.
