The Variant Effect Predictor (VEP) community tool predicts the impact of non-synonymous single amino acid variants. The tool is available from the &quot;Community&quot; section in the left menu for all neXtProt entries. Any isoform can be selected provided it aligns perfectly with an ENSP. All sequence features for the isoform are displayed to provide the context for the variants selected. The SIFT ([Kumar, Henikoff and Ng, 2009](https://doi.org/10.1038/nprot.2009.86)) and PolyPhen-2 ([Adzhubei _et al._, 2010](https://doi.org/10.1038/nmeth0410-248)) scores for the selected variant(s) are obtained from the Ensembl VEP tool ([McLaren _et al._, 2016](https://genomebiology.biomedcentral.com/articles/10.1186/s13059-016-0974-4)).

By zooming in on a region of the sequence, one or more variants can be selected by simply clicking on a residue in the sequence and providing the variant amino acid, followed by clicking on the &quot;Get Predictions&quot; button. The &quot;+ Add Variants&quot; button allows one to select multiple variants in one go by entering their position in the sequence and variant amino acid, and obtain their predicted effect by clicking on the &quot;Get Predictions&quot; button. It is also possible to upload a CSV file containing the position in the sequence, the original and variant amino acid for each variant and get their predicted impact. The SIFT and PolyPhen-2 scores are returned in the variant table, which can be exported in CSV format.

The VEP tool can be used to:

1. Determine which amino acid residues should be modified for _in vitro_ mutagenesis experiments,
2. Classify variants associated with a disease based on their potential impact,
3. Distinguish between variants of uncertain (or unknown) significance (VUS),
4. Investigate whether any known SNPs may have a deleterious effect, or
5. Predict whether residues in specific domains or regions are critical or not.
