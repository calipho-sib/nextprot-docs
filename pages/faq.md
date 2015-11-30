#FAQ (Draft under development ...)

## FAQ_001 How is neXtProt different from Uniprot?

## FAQ_002 How do we compute protein existence ?

By default each entry is given the protein existence level (PE) assigned by UniProt. See http://www.uniprot.org/help/protein_existence .
Then we use the proteomics data we obtain from other data sources (mainly PeptideAtlas) to increase to PE1 the protein existence level of entries having experimental evidence at transcript level (PE2), protein existence inferred from homology (PE3) and protein predicted (PE4).

To promote a protein to PE1 , we need to have one unique peptide of at least 9 aa identified in a biological sample.
For example In the case of A6NN73 four peptides have been identified in biological samples, but none of them is unique (they are labelled 
" found in other entries"). Therefore we cannot validate the existence of the protein.

SRM peptides cannot be used to validate the existence of proteins because they are synthetic peptides used as reagents, 
not biological peptides observed in samples.

## FAQ_003 How are the different protein isoforms aligned?

**TODO**
Pour repondre d'une facon simple a l'utilisateur, tu peux résumer la situation en disant que l'alignement des isoformes entre-elles est déduit de leur alignement sur le genome quand celui-ci est possible, sinon des informations données par UniProtKB concernant la facon dont les isoformes diffèrent de la séquence canonique ("The sequence of this isoform differs from the canonical sequence as follows").
genome quand celui-ci est possible, sinon des informations données par UniProtKB concernant la facon dont les isoformes diffèrent de la séquence canonique ("The sequence of this isoform differs from the canonical sequence as follows").

Si c'est pour une documentation plus technique:

1. load des ENSG: accession code, chromsome, position sur le chromosome, band, strand, name
2. load des ENSE (exons): accession code, position sur le gene, sequence
3. load des ENST (transcripts): accession code, sequence, composition en exons, position sur le gene
4. alignement de la sequence des isoformes sur la sequence des transcripts, selection du ou des ENST sur lesquels l'isoforme s'aligne
5. positionnement des isoformes sur le genome, deduit de leur alignement sur les transcripts
6. si toutes les isoformes s'alignent sur le genome, construction de la master, qui est alors equivalente au gene, la position des isoformes sur la master etant egale a la position des isoformes sur le gene.
7. si au moins une isoforme ne s'aligne pas sur le genome, construction de la master que est alors equivalent a un gene reconstitue par reverse engineering a partir des informations de composition des isoformes donnees par UniProt.
    on peut considerer les informations donnees par UniProt comme une sorte d'alignement des isoformes entre elles.


## FAQ_004 Not all of the Ensembl isoforms are present. Based on what criteria are the other sequences discarded?
