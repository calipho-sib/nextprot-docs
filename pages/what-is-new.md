#What's new?

**April 11, 2016**

1. The search in the HOME page now always includes the "Gold only" and "Include silver" options.
2. It is now possible to search for a publication DOI in the simple search.
3. A new version of the XML and the corresponding XSD (XML Schema Definition) are provided. This new version: (1) reflects the RDF data model implemented, (2) includes all the data in neXtProt (for instance it now includes peptides mapped to entries), and (3) makes use, whenever possible, of the same format for controlled vocabulary terms, cross-references, identifiers and publication. In order for users to make a gradual transition to this new format, we will continue to provide the neXtprot releases in the old format until 2017. Please refer to the FTP [README](ftp://ftp.nextprot.org/README) for the location of these files.
4. Additional data, including topological domains and membrane, are now shown in the new peptide viewer which is under construction.
5. Documentation on [Citing neXtProt](https://search.nextprot.org/citing-nextprot) is now online.

**February 12, 2016**

1. The latest data release (neXtProt release 2016-01-11) is implemented in this new version. For details, refer to the [February 2016 neXtProt release notes](http://www.nextprot.org/news/nextprot/2016-02-12/february-2016-nextprot-release).
2. The HOME page now links to [The human proteome](https://search.nextprot.org/human-proteome) information page.
3. A new [protein existence view](https://search.nextprot.org/view/statistics/protein-existence) showing the detailed distribution of the "protein existence" status of the entries across chromosomes for the release is now available.
4. The [Download](https://search.nextprot.org/help/learn-download) documentation page has been updated to include the ttl files available from our FTP site.

**November 30, 2015**

1. A new, re-designed HOME page is implemented in this new version. Four pannels, "Getting started", "Data sources", "News" and a release pannel link to documentation, sources of data integrated in neXtProt, news (release, research and press releases), and release contents and statistics.
2. Additional publications are now exported in the XML.
3. Excel (.xls) export file now includes all gene names and chromosomal locations for an entry.
4. Searches in publications which include "and", "the", etc. no longer return no results.

**September 24, 2015**

1. The latest data release (neXtProt release 2015-09-01) is implemented in this new version. For details, refer to the [September 2015 neXtProt release notes](http://www.nextprot.org/news/nextprot/2015-09-24/september-2015-nextprot-release).
2. Lists can now be created by entering or uploading a file with UniProtKB accession numbers.
2. Multiple list files can be uploaded to generate a single list.
3. When creating a new list which includes an invalid accession number, an error message is displayed and the list is not created.
4. The ChEMBL, IPI and MIM identifiers are exported in the XML.
5. Search results and protein lists can now be downloaded as protein or protein isoform lists in Excel format (.xls).

**July 16, 2015**

1. Sequences (FASTA) and accession numbers (TXT) for protein search results and list contents can now be downloaded. Unless a sort order has been specified, the data is listed in alpha-numerical order of the entry accession number.
2. All protein and gene names, as well as gene chromosomal location, exons and transcripts are now available in the API.

**May 12, 2015**

1. The latest data release (neXtProt release 2015-04-28) is implemented in this new version.
2. The issues with the simple search autocomplete have been fixed. The autocomplete no longer concatenates words or acts weird if the query input is in upper case. In addition, the first option in the autocomplete dropdown is no longer selected by default when entering Return or clicking on the Search button.

**February 14, 2015**

1. The graphical user interface (GUI) has been completely revamped.
2. This new version runs on the latest data release (neXtProt release 2015-01-01).
3. The underlying data model has evolved. However, please be aware that it is still undergoing changes.
4. Protein lists are no longer public. You need to login to save and manage your lists. 
5. Documentation for the simple and advanced search is now available from the **Help** menu.
