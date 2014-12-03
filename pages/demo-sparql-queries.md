Q001 phosphorylated and located in the cytoplasm


```
select distinct ?entry where {
 ?entry :isoform ?iso .
 ?iso :keyword / :in term:KW-0597 .
 ?iso :location /:in /:childOf term:SL-0086 .
}order by ?entry
```


Q002 that are located both in the cytoplasm and in the nucleus


```
select distinct ?entry where {
  ?entry :isoform ?iso.
  ?iso :location / :in / :childOf term:SL-0086, term:SL-0191
}order by ?entry
```


Q003 with 37 transmembrane regions or more


```
select distinct ?entry where{
 ?entry :isoform ?iso.
   ?iso :topology ?statement .
   ?statement a :TransmembraneRegion.
}
GROUP BY ?entry ?iso 
HAVING(count( ?statement)>=37)
```


Q004, Proteins highly expressed in brain but not expressed in testis


```
SELECT distinct ?entry WHERE {
# get all expression
  ?entry :isoform/:expression ?s1,?s2.

# highly expressed in brain
  ?s1 :in/:childOf  term:TS-0095;:withEvidence/:expressionLevel :High.

# not expressed in testis
  ?s2 :in/:childOf  term:TS-1030;:withEvidence/:expressionLevel :Negative.
}
```


Q005 located in mitochondrion and that lack a transit peptide


```
select distinct ?entry where{
 ?entry :isoform ?iso .
  ?iso :location/:in/:childOf term:SL-0173 .
  FILTER NOT EXISTS{ ?iso :keyword term:KW-0809 }
}order by ?entry
```


Q006 whose genes are on chromosome 2 and linked with a disease


```
select distinct ?entry where {
   ?entry :gene / :chromosome  "13"^^xsd:string;
   :isoform / :medical /rdf:type :Disease.
}
```


Q007 linked to diseases that are associated with cardiovascular aspects


```
select distinct ?entry  WHERE {
  ?entry :isoform /:medical / :in /:related / :childOf term:D002318.
}
```


Q008 whose genes are less than 50000 bp away from the location of the gene of protein Y


```
select distinct ?entry where {
   #example with P53
   entry:NX_P04637 :gene /:begin ?s;:gene/:chromosome ?chr.
   ?entry :gene/:begin  ?gs;:gene/:chromosome ?chr.
   FILTER( ?gs > (?s -50000) && ?gs <= (?s +50000) && ?entry != entry:NX_P04637)
}
```


Q009 with 3 disulfide bonds and that are not hormones 


```
#pending
#note: filter not exists { ?entry :classifiedWith  term:KW-0372 . } 
#note: is more stringent than 
#note: filter not exists { ?isoform :keyword  term:KW-0372 . }
select distinct ?entry   WHERE {
  ?entry :isoform ?isoform.
  ?isoform :ptm ?statement .
  ?statement a :DisulfideBond.
  filter not exists { ?isoform :keyword  term:KW-0372 . }
  filter not exists { ?entry  :isoform / :function  / :in term:GO_0005179  . }
} GROUP by ?entry ?isoform HAVING (count(?statement) =3 )
```


Q010 that are glycosylated and not located in the membrane


```
select  distinct  ?entry WHERE  {
  ?entry :isoform ?iso .
  ?iso :keyword / :in term:KW-0325.
  FILTER NOT EXISTS { ?iso :topology / :in term:CVTO_0022 }
}
```


Q11 Proteins that are expressed in liver and involved in transport


```
#time:
# (transport term:GO_0006810, term:KW-0813) 
SELECT distinct ?entry WHERE {
  ?entry :isoform ?iso .
  ?iso :expression/:in/:childOf term:TS-0564.
  ?iso :keyword / :in term:KW-0813. 
}
```


Q012 that interact with protein Y and that are involved in splicing


```
select distinct ?entry WHERE  {
  entry:NX_Q96I25 :isoform / :interaction / :with ?entry.
  ?entry :isoform / :keyword / :in term:KW-0508
}
```


Q013 with a protein kinase domain but no kinase activity


```
SELECT distinct ?entry WHERE {
  ?entry :isoform ?iso .
  ?iso :region /:in term:DO-00529.
  FILTER NOT EXISTS { ?iso :enzymeClassification / :in /:childOf term:2_7_-_- }
}
```


Q014 with 2 SH3 domains and 1 SH2 domain


```
select distinct ?entry  where{
?entry :isoform ?iso.
#with 1 SH3
  {select ?iso where{?iso :region ?stat1. ?stat1 :in term:DO-00614}GROUP BY ?iso  HAVING(count( ?stat1)=1)}

#with 2 SH2
  {select ?iso where{?iso :region ?stat2. ?stat2 :in term:DO-00615}GROUP BY ?iso HAVING(count( ?stat2)=2)}
}GROUP BY ?entry
```


Q015 Proteins with a PDZ domain that interact with at least 1 protein which is expressed in brain


```
SELECT distinct ?entry WHERE {
?entry :isoform ?iso.
?iso :region / :in term:DO-00477. #PDZ domain
?iso :binaryInteraction/:with/:isoform?/:expression/:in/:childOf term:TS-0095 #brain
}
```


Q016 with a mature chain <= 1000 amino acids which are secreted and do not contain cysteines in the mature chain


```
#time:0.08
SELECT distinct ?entry  WHERE  {
?entry :isoform ?iso .
?iso :location/:in term:SL-0243;:sequence / :chain ?seq. #secreted
?iso :matureProtein [ :start ?mstart ; :end ?mend]
FILTER ((?mend-?mstart > 0) && (?mend-?mstart <= 1000))	 
BIND(?mend - ?mstart as ?mlen)	 
BIND(substr(?seq, ?mstart, ?mlen) as ?mseq)	 
filter(!regex (?mseq,'C'))
}
```


Q017 Proteins >=1000 amino acids and located in nucleus and expression in nervous system


```
#pending
#time:1.159
SELECT distinct ?entry WHERE  {
  ?entry :isoform ?iso.
  ?iso :location/:in/:childOf term:SL-0191.
  ?iso :expression/:in/:childOf term:TS-1313.
  ?iso :sequence/:length ?len.
  FILTER (?len>1000)
}
```


Q017b Proteins >=1000 amino acids and located in nucleus and expression in nervous system


```
#pending
#time:490.051
#see: Q017 is a lot more efficient !
SELECT distinct ?entry WHERE  {
  ?entry :isoform ?iso.
  ?iso :location/:in/:childOf term:SL-0191.
  ?iso :expressionProfile ?p.
  ?p :in/:childOf term:TS-1313.
  ?p :withEvidence / :expressionLevel ?level.
  ?iso :sequence/:length ?len.
  FILTER (?len>1000)
  FILTER (?level != :Negative)
}
```


Q18 that are acetylated and methylated and located in the nucleus


```
#time:8.564
#pending
select distinct ?entry where {
  ?entry :isoform ?iso .
  ?iso :location/:in/:childOf term:SL-0191.
# acetylated and methylated
  ?iso :keyword/:in term:KW-0007,term:KW-0488.
}
```


Q020, Proteins with >=2 HPA antibodies whose genes are located on chromosome 21 and that are highly expressed at IHC level in heart


```
#time:1.269
#pending
select ?entry  where {
  select distinct ?entry ?ac where {
    
    ?entry :gene / :chromosome "21"^^xsd:string .

    ?entry :isoform / :expressionProfile ?s1.
    ?s1 :in / :childOf  term:TS-0445 .
    ?s1 :withEvidence ?evi .
    ?evi :expressionLevel :High .
    ?evi :experimentalContext / :detectionMethod term:ECO_0000045.

    ?entry :isoform / :mapping ?map .
    ?map a :AntibodyMapping .
    ?map :reference ?ref .
	?ref :provenance db:HPA; :accession ?ac .
  }
} group by ?entry 
having (count(?ac)>=2)
```


Q021 with >=1 HPA antibody and located in the peroxisome


```
#time:0.572
select  distinct ?entry  where {
 ?entry :isoform ?iso . 
  
  ?iso :mapping ?map . 
  ?map a :AntibodyMapping; :reference / :provenance db:HPA
		 
  {?iso :keyword / :in term:KW-0576 .}
  UNION 
  {?iso :subcellularLocation / :in /:childOf term:SL-0204. } 
  UNION 
  {?iso :goCellularComponent / :in /:childOf term:GO_0005777.}  
}
```


Q022 Proteins with no function annotated 


```
#time:0.544
#pending
select distinct ?entry where  {
  ?entry :isoform ?iso.
  FILTER NOT EXISTS {?iso :function ?_ }
} order by ?entry
```


Q023 that are involved in transport and located in a membrane and that are not glycosylated (experimentally or predicted)


```
#time:3.514
select distinct ?entry where {
# term:KW-0472 membrane
# term:SL-0162 membrane
# term:KW-0813 transport
# term:GO_0006810 transport
# KW-0325 glycoprotein
  ?entry :isoform  ?iso .
  {
	?iso :goBiologicalProcess / :in / :childOf term:GO_0006810.
  } union {
    ?iso :keyword / :in term:KW-0813.
  }
  {
	?iso :keyword / :in term:KW-0472.
  } union {
	?iso :location / :in /:childOf term:SL-0162.
  }  
  filter not exists { ?iso :keyword / :in term:KW-0325 } 
}
```


Q024 with more than 1 reported gold interaction


```
#time:0.559
#pending
select  distinct ?entry where {
  ?entry :isoform/:binaryInteraction ?interaction.
  ?interaction :with ?interactant; :quality :GOLD
} 
group by ?entry
having count(distinct ?interactant) > 1
```


Q025 with >=50 interactors and not involved in a disease


```
#time:1.283
#pending
# we exclude both disease annotation ans reference to Orphanet
select distinct ?entry  where {
  ?entry :isoform ?iso.
  ?iso :binaryInteraction/:with ?interactant .
  FILTER NOT EXISTS { ?entry :reference / :provenance db:Orphanet . }
  FILTER NOT EXISTS {   ?iso :medical / rdf:type :Disease. }
}group by ?entry ?iso having (count(?interactant) >= 50)
```


Q026 interacting one protein ore more which are located in the mitochondrion


```
#time:0.552

select distinct ?entry where {
  ?entry :isoform/:interaction/:with ?interactant.
  # :isoform predicate in line below is optional (postfix ?) because the data model
  # allows the ?interactant to be either an :Entry or an :Isoform 
  ?interactant :isoform?/:location/:in/:childOf term:SL-0173 
}group by ?entry
limit 100
```


Q027 with one or more glycosylation sites reported in PubMed:X or PubMed:Y


```
#time:0.38

select distinct ?entry ?pub where{
 values ?publications {"PubMed:20570859"^^xsd:string "PubMed:14760718"^^xsd:string}
# get all assertions from the publications
 ?entry :isoform/:glycosylationSite ?statement.
 ?statement :withEvidence/:publication/:from ?publications
}
```


Q028 linked with a disease but without a disease-linked variant


```
#time:2.147
select distinct ?entry where {
  ?entry :isoform / :medical / rdf:type :Disease .
  filter  ( not exists { ?entry :isoform / :variant / :disease ?_ . } )
}
```


Q029 linked with a disease but without a disease-linked variant


```
#time:0.384
select distinct ?entry where {
  ?entry :isoform/:medical/:in/:related/:childOf term:D002318.
}
```


Q030 whose gene is located in chromosome 2 that belongs to families with >=5 members in the human proteome


```
#time:0.456

select ?entry  where{
  ?entry :family/:accession/^:accession/^:family ?member.
  ?entry :gene / :chromosome "2"^^xsd:string .
} group by ?entry  having ( count(?member) >= 5 )
```


Q030b whose gene is located in chromosome 2 that belongs to families with >=5 members in the human proteome


```
#time:0.415
select distinct ?entry  where{
#select family with >=5 members
  {select ?family where{?family ^:accession/^:family ?entry}group by ?family  having ( count(?entry) >= 5 )}
#constraint with chromosome 2  
  ?entry :gene / :chromosome "2"^^xsd:string;:family/:accession ?family.
}
```


Q031  with >=10 "splice" isoforms


```
#time:0.28
select distinct ?entry   WHERE  {
  ?entry :isoform ?iso.
} group by ?entry having(count(?iso)>=10)
```


Q032 with a coiled coil region and involved in transcription but does not contain a bZIP domain


```
#time:0.21
select distinct ?entry where {
 ?entry :isoform ?iso;:classifiedWith term:KW-0804.
 ?iso :region/rdf:type :CoiledCoilRegion.
 FILTER NOT EXISTS{
   ?iso :region/:in term:DO-00078
 }
}
```


Q033 with >=1 phoshotyrosine but no phosphoserine or phosphothreonine


```
#time:0.08
select distinct ?entry where {
select ?entry ?iso (count(?ptm)) where {
  ?entry :isoform ?iso .
  ?iso :modifiedResidue  ?ptm .
  ?ptm :in term:PTM-0255 #phosphotyrosine .
  filter (
    not exists { ?iso :modifiedResidue / :in term:PTM-0253 . } #phosphoserine
    &&
    not exists { ?iso :modifiedResidue / :in term:PTM-0254 . } #phosphothreonine
  )
}
group by ?entry ?iso
having ( count(?ptm) >= 1 )
}
```


Q034 with >=1 homeobox domain and with >=1 variant in the homeobox domain(s)


```
#time:0.15
SELECT distinct ?entry WHERE {
    ?entry :isoform ?iso.
# with >=1 homeobox domain
    ?iso  :region  ?st1.
    ?st1 :in term:DO-00312;:start ?start;:end ?end.
# with >=1 variant
    ?iso  :variant  ?var.
    ?var :start ?varpos.
# one variant in the homeobox domain
    FILTER (?varpos >=?start && ?varpos <=?end)
}
```


Q035  located in the mitochondrion and which is an enzyme


```
#time:0.08
SELECT distinct  ?entry   WHERE  {
  ?entry :classifiedWith/rdf:type :EnzymeClassificationOntology.
  ?entry :isoform/:location/:in/:childOf term:SL-0173
}
```


Q036 that are oxidoreductases and bind NAD/NADP


```
#time:0.1
SELECT distinct ?entry  WHERE  {
  ?entry :classifiedWith term:KW-0560. #oxidoreductase
  ?entry :classifiedWith ?kw
FILTER( ?kw in (term:KW-0520,term:KW-0521)) # NAD or NADP
}
```


Q037 that bind RNA but do not contain a RRM domain


```
#time:0.1
SELECT distinct ?entry WHERE {
 ?entry :isoform ?iso;:classifiedWith term:KW-0694.
 FILTER NOT EXISTS {?iso :region/:in term:DO-00581}
}
```


Q038 with >=1 selenocysteine in their sequence


```
#time:0.1
SELECT distinct ?entry WHERE  {
  #?entry :isoform/:selenocysteine/:in ?statement.
  ?entry :isoform/ :keyword / :in term:KW-0712. # selenocysteine
}
```


Q039 with >=1 mutagenesis in a position that correspond to an annotated active site


```
#time:0.1
SELECT distinct ?entry WHERE  {
  #?entry :classifiedWith/rdf:type :EnzymeClassificationOntology;:isoform ?iso.
  ?entry :isoform ?iso.
  ?iso :mutagenesis /:start ?mutaPos.
  ?iso :activeSite /:start ?actsitePos.
  FILTER(?mutaPos=?actsitePos)
}
```


Q040 that are enzymes and with >=1 mutagenesis that "decrease" or "abolish" activity


```
#time:0.3
SELECT distinct ?entry WHERE  {
  ?entry :classifiedWith/rdf:type :EnzymeClassificationOntology;:isoform ?iso.
  ?iso :mutagenesis/rdfs:comment ?comment
FILTER regex(?comment, '(decrease|abolish).*activity','i')
}
```


Q041 that are annotated with GO "F" terms prefixed by "Not"


```
#time:0.26
SELECT distinct ?entry WHERE  {
  ?entry :isoform ?iso.
  ?iso :goMolecularFunction ?statement.
  ?statement :withNegativeEvidence ?ev.
}
```


Q042 that bind a metal and are secreted


```
#time:0.1
SELECT distinct ?entry WHERE {
 ?entry :isoform ?iso .
 #?iso :location/:in/:childOf term:SL-0243 .
 ?iso :keyword / :in term:KW-0964. # secreted
 ?iso :keyword / :in term:KW-0479. # metal-binding
}
```


Q043  that bind zinc and are not oxidoreductase and not involved in transcription


```
#time:0.45
SELECT distinct ?entry WHERE {
 ?entry :isoform ?iso .
 ?iso :keyword / :in term:KW-0479. # metal-binding
 ?iso :keyword / :in term:KW-0862. # zinc
FILTER NOT EXISTS { ?iso :keyword / :in term:KW-0804} # transcription
FILTER NOT EXISTS {?iso :keyword / :in term:KW-560 } # oxidoreductase
}
```


Q044  involved in the X pathway (from reactome for example)


```
#time:4.6
select distinct ?entry where {
  ?entry :isoform / :function / a :Pathway .
  ?entry  :reference / :provenance db:Reactome .
}
```


Q045 with >=1 active sites that is a proton acceptor


```
#time:0.07
SELECT distinct ?entry ?comment WHERE  {
  ?entry :isoform/ :activeSite /rdfs:comment ?comment.
  filter (contains (?comment,'Proton acceptor'))
  }
```


Q046  with a gene alternative name which is IL27


```
#time:

select distinct ?x ?p ?entry ?name where {
 ?entry a :Entry.
  ?entry :alternativeName /:fullName ?name.
 FILTER (strlen(?name) < 5 )
}
```


Q047  with a gene name CLDN*


```
#time:0.1
select distinct ?entry where {
  ?entry :gene / :name ?name .
  filter (regex(?name, "^CLDN"@en))
}
```


Q048 with >=1 variants of the type "C->" (Cys to anything else) that are linked to >=1 disease


```
#time:0.36
SELECT distinct ?entry ?v  WHERE  {
  ?entry :isoform ?iso.
  ?iso :variant ?statement;:medical/rdf:type :Disease.
  ?statement :original "C"^^xsd:string;:variation ?v
}

# or more precisely with disease directly corelated to the variant itself
#SELECT distinct ?entry WHERE  {
#  ?entry :isoform / :variant ?variant .
#  ?variant :original "C"^^xsd:string;:variation ?v.
#  ?variant :disease ?someDisease .
#}
```


Q049  with >=1 variants of the types "A->R" or "R->A"


```
#time:0.39
SELECT distinct ?entry WHERE  {
  ?entry :isoform/:variant ?statement.
  {?statement :original "A"^^xsd:string;:variation "R"^^xsd:string}
  UNION
  {?statement :original "R"^^xsd:string;:variation "A"^^xsd:string}
}
```


Q050  which are expressed in brain according to IHC but not expressed in brain according to microarray


```
#time:33.8
SELECT distinct ?entry WHERE {
  ?entry :isoform ?iso.
  ?iso :expressionProfile ?s1;:expressionProfile ?s2.

# there exists an evidence exists saying that microarray didn't not detect any expression in the brain
  ?s2 :in/:childOf  term:TS-0095;:withNegativeEvidence/:experimentalContext/:detectionMethod term:ECO_0000220.

# there exists an evidence telling that the protein is expressed in brain according to IHC
  ?s1 :in/:childOf  term:TS-0095;:withEvidence/:experimentalContext/:detectionMethod term:ECO_0000045.

}
```


Q051  with >=1 NMR 3D structures


```
#time: 0.37
SELECT distinct ?entry WHERE {
  ?entry :isoform ?iso.
  ?iso :pdbMapping ?map.
  ?map :method ?meth
  FILTER(contains(?meth,'NMR'))
 }
```


Q052 with a sequence that does not contain a lysin in the mature region


```
#time:0.6
SELECT distinct ?entry WHERE {

?entry :isoform ?iso .
?iso :sequence / :chain ?seq.
?iso :matureProtein [ :start ?mstart ; :end ?mend]
FILTER (?mend-?mstart > 0)	 
BIND(?mend - ?mstart as ?mlen)	 
BIND(substr(?seq, ?mstart, ?mlen) as ?mseq)	 
#BIND(substr(?seq, ?mstart, ?mend - ?mtart) as ?mseq)	 
filter(!regex (?mseq,'K'))
}
```


Q053   which are involved in cell adhesion according to GO with an evidence not IAE and not ISS


```
#time: 0.48
SELECT distinct ?entry WHERE {
 ?entry  :isoform/:function ?statement.
 ?statement :in / :childOf term:GO_0007155.
 ?statement :withEvidence/:code ?ecode .
  FILTER  ( ?ecode != :IEA && ?ecode != :ISS)
}
```


Q054   which are "Receptor binding" according to GO and Swiss-Prot keyword "Immunity"


```
#time: 0.1
select distinct ?entry where {
  ?entry :isoform ?iso.
  ?iso :function ?statement.
  ?statement :in / :childOf term:GO_0005102.
  ?iso :keyword/:in term:KW-0391.
}
```


Q055 which have genes of length >=2000000 bp


```
#time:0.1
select distinct ?entry  where {
  ?entry :gene / :length ?l .
  filter (?l >= 2000000)
}
order by DESC(?l)
```


Q056  which have genes with exactly 1 coding exon


```
#time: 
SELECT distinct ?entry  WHERE  {

}
```


Q057  which are located in mitochondrion with an evidence other than HPA and DKFZ-GFP


```
#time: 0.25
select distinct ?entry where {
 ?entry :isoform ?iso .
  ?iso :location ?loc.
  ?loc :in/:childOf term:SL-0173 .
  ?loc :withEvidence /:assignedBy ?src.
  FILTER  ( ?src not in (source:Human_protein_atlas_subcellular_localization, source:GFP-cDNAEMBL))
  # alternatively
  #?loc :withEvidence /:fromXref ?xr.
  #FILTER  ( ?xr not in (db:HPA, db:GFP-cDNA))
}
```


Q058  which are located on the genome next to a protein which is involved in spermatogenesis


```
#time: 
SELECT distinct ?entry  WHERE  {
  ?entry :isoform ?iso.
}
```


Q059  that are glycosylated and phosphorylated on an extracellular topological domain


```
#time: 4.85
select  distinct ?entry where {
 ?entry :isoform ?iso .
 ?iso :topologicalDomain ?topodom.
  ?topodom :in term:CVTO_0002 .
  ?topodom :start ?topostart ; :end ?topoend.
 ?iso :positionalAnnotation ?annot.
  {
	?annot a :ModifiedResidue.
	?annot :in ?ptmtype.
	FILTER (?ptmtype in (term:PTM-0253, term:PTM-0254, term:PTM-0255))  
  }
  union
  {
  ?annot a :GlycosylationSite.
  }
 ?annot :start ?ptmpos.
  FILTER((?ptmpos >= ?topostart) && (?ptmpos <= ?topoend))
}
```


Q060  which have >=1 negatively charged residue (in set DE) in a transmembrane domain


```
#time: 0.58
SELECT distinct ?entry WHERE {
 ?entry :isoform ?iso .
 ?iso :transmembraneRegion  ?tm.
 ?tm :start ?tmstart ; :end ?tmend.
 ?iso :sequence /:chain ?chain.
  BIND (substr(?chain, ?tmstart, ?tmend-?tmstart) as ?tmseq)
  FILTER(regex(?tmseq, '[DE]'))

}
```


Q061  which have >=1 3D structure that spans the complete sequence of the mature protein


```
#time: 0.23
SELECT distinct ?entry WHERE {
  ?entry :isoform ?iso.
 ?iso :pdbMapping  ?pdbmap.
 ?pdbmap :start ?pdbstart ; :end ?pdbend.
 ?iso :matureProtein [ :start ?mstart ; :end ?mend]
 FILTER (?mend-?mstart > 0)	 
 FILTER((?pdbstart <= ?mstart) && (?pdbend >= ?mend))
}
```


Q062 which have >=1 zinc finger of any subtype


```
#time: 0.26
SELECT distinct ?entry WHERE {
?entry :isoform ?iso .
?iso :zincFingerRegion ?_.
}
```


Q063 which have >=1 RRM RNA-binding domain and either no GO "RNA binding" or a GO "RNA binding" with evidence IEA or ISS


```
#time: 0.1
SELECT distinct ?entry  WHERE {
 ?entry :isoform ?iso
 {
#>=1 RRM RNA-binding domain
  ?iso :region/:in term:DO-00581.

#GO "RNA binding" with evidence IEA or ISS
  FILTER NOT EXISTS {
   ?iso :function/:in /:childOf term:GO_0003723
  }
 }UNION{
#>=1 RRM RNA-binding domain
  ?iso :region/:in term:DO-00581.

#GO "RNA binding" with evidence IEA or ISS
  ?iso :function ?s1.
  ?s1 :in /:childOf term:GO_0003723;:withEvidence/:code ?type.
  values ?type {:IEA :ISS}

 }
}
```


Q064 which are enzymes with an incomplete EC number


```
#time: 0.18
select distinct ?entry where {
  ?entry :isoform / :function / a :Pathway .
  ?entry  :reference / :provenance db:Reactome .
}
```


Q065  with >1 catalytic activity


```
#time: 0.3
SELECT distinct ?entry    WHERE  {
  ?ec a :EnzymeClassificationOntology.
  ?entry :classifiedWith ?ec
}GROUP BY ?entry HAVING (count(?ec)>1)
```


Q066  that are cytoplasmic with alternate O-glycosylation or phosphorylation at the same positions


```
#time: 0.9
select  distinct ?entry where {
 ?entry :isoform ?iso .
 ?iso :location/:in/:childOf term:SL-0086.
 ?iso :modifiedResidue /:in ?ptmtype.
 ?iso :modifiedResidue /:start ?ptmpos.
 FILTER (?ptmtype in (term:PTM-0253, term:PTM-0254, term:PTM-0255))  
?iso :glycosylationSite /:start ?ptmpos.
}
```


Q067 with alternative acetylation or Ubl conjugation (SUMO or Ubiquitin) at the same positions


```
#time: 0.4
 SELECT  distinct ?entry  WHERE  {
  ?entry :isoform ?iso.
    ?iso :crossLink /:start ?ptmpos.
    ?iso :modifiedResidue ?ptm .
    ?ptm :start ?ptmpos.
    ?ptm rdfs:comment ?comment.
# use this filter to select acetylations
  FILTER regex(?comment, "acetyl","i")
}
```


Q068  with protein evidence PE=2 (transcript level)


```
#time: 0.45
SELECT distinct ?entry  WHERE  {
  ?entry :existence :Evidence_at_transcript_level
}
```


Q069  phosphorylated by SRC


```
#time: 0.25
select  distinct ?entry where {
 ?entry :isoform ?iso .
    ?iso :modifiedResidue ?ptm .
    ?ptm :in ?ptmtype.
    ?ptm rdfs:comment ?comment.
  FILTER (?ptmtype in (term:PTM-0253, term:PTM-0254, term:PTM-0255))  
  FILTER regex(?comment, "SRC","i")
 }
```


Q070 secreted but without a signal sequence


```
#time: 0.12
select distinct ?entry where {
  ?entry :isoform ?iso.
    ?iso :location/:in/:childOf term:SL-0243
 FILTER NOT EXISTS {?iso :signalPeptide ?_}
 # the filter should apply to displayed entry only
}
```


Q071 associated with >3 papers that are not "large scale" and not "additional"


```
#time:
SELECT distinct ?entry WHERE {
  ?entry :isoform ?iso .
}
```


Q072 with a cross-reference to CCDS


```
#time: 3.6
SELECT distinct ?entry WHERE {
?entry :reference  / :provenance db:CCDS .
# we don't have the info linking CCDS to isoforms
}
```


Q073 with no domain


```
#time: 2.4
select distinct ?entry where{
  ?entry a :Entry .
  FILTER NOT EXISTS { ?entry :isoform / :region/rdf:type :Domain}
}
```


Q074 belonging to a family with at least 1 other member in human


```
#time: 4.7
select distinct ?entry 
where {
  ?entry :family/:accession/:childOf ?ac .
  ?member :family/:accession/:childOf ?ac .
} 
group by ?entry
having (count(distinct ?member) >= 2 )
```


Q075  which have been detected in the HUPO liver proteome set but not the HUPO plasma proteome set


```
#time: 10s
select distinct ?entry where {
  ?entry a :Entry .
  ?entry :isoform / :mapping / :withEvidence / :assignedBy source:PeptideAtlas_human_liver .
  filter NOT EXISTS {
    ?entry :isoform / :mapping / :withEvidence / :assignedBy source:PeptideAtlas_human_plasma .
  }
}
```


Q076  which are located in mitochondrion and have >=1 HPA antibody and exist in >=1 proteome identification sets


```
#time: 0.4
select  distinct ?entry where {
 ?entry :isoform ?iso .
 ?iso :location/:in/:childOf term:SL-0173.
  ?iso :mapping ?map1.
 ?map1 a :AntibodyMapping.
  ?iso :mapping ?map2.
 ?map2 a :PeptideMapping.
 # the nb is the same if I dont filter on PeptideMapping
}
```


Q077  which are expressed in liver according to IHC data but not found in HUPO liver proteome set


```
#time: 10.7
select distinct ?entry where {
  ?entry :isoform /:expression ?s1.
  ?s1 :withEvidence ?evi;:in/:childOf term:TS-0564. #Liver
  ?evi :experimentalContext / :detectionMethod / rdfs:subClassOf :IHC; :expressionLevel ?level .
  filter (?level not in (:Negative))
  FILTER NOT EXISTS {
    ?entry :isoform / :mapping / :withEvidence / :assignedBy source:PeptideAtlas_human_liver .
  }
}
```


Q078  which have been identified in any proteomics set and that are secreted


```
#time: 0.13
SELECT distinct ?entry  WHERE  {
 ?entry :isoform ?iso.
  ?iso :location/:in/:childOf term:SL-0243.
   ?iso :peptideMapping ?map.
}
```


Q079  with >=1 3D structure and are phosphorylated


```
#time: 0.53
select distinct ?entry where {
 ?entry :isoform ?iso .
 ?iso :keyword / :in term:KW-0597 . #phosphoprotein
 ?iso :pdbMapping ?map.
}
```


Q080 with >=1 3D structure of resolution <=X Angstroms


```
#time: 0.76
select distinct ?entry where {
 ?entry :isoform ?iso .
 ?iso :pdbMapping ?map.
  ?map :resolution ?res.
 FILTER(?res <= 3.0)
}
```


Q081  with >=1 3D structure and are located in the mitochondrion and are linked with a disease


```
#time: 0.1
SELECT distinct ?entry WHERE {
  ?entry :isoform ?iso.
  ?iso :pdbMapping ?map.
  ?iso :location/:in/:childOf term:SL-0173 .
  ?iso :medical/rdf:type :Disease.
 }
```


Q082  whose genes are on chromosome n that have "gold" variants not linked to disease (ie polymorphisms)


```
#time: 0.1
SELECT distinct ?entry WHERE  {
  ?entry :gene / :chromosome "18"^^xsd:string; :isoform / :variant ?variant .
  ?variant :withEvidence / :quality :GOLD .
 FILTER NOT EXISTS { ?variant :disease ?disease . }
}
```


Q083 whose genes are on chromosome n that are expressed only a single tissue/organ


```
#time: 
SELECT distinct ?entry count(?tiss) WHERE {
  ?entry :gene / :chromosome "18"^^xsd:string .
  ?entry :isoform  ?iso.
  ?iso :expressionProfile /:in ?tiss.
  ?iso :expressionProfile /:in  /:childOf term:TS-0564. #liver
  # find topmost parent and only count it
}
#GROUP BY ?entry ?iso HAVING(count(?tiss) < 5)
#FILTER(count(?tiss) < 5))
limit 50
```


Q084  whose genes are on chromosome n that are known to be glycosylated or phosphorylated or acetylated (excluding prediction)


```
#time: 
select distinct ?entry {
  ?entry :gene / :chromosome "18"^^xsd:string .
  ?entry :isoform  ?iso.
  ?iso :glycosylationSite /:withEvidence /:code ?evcode.
  filter (?evcode not in (:IEA))

}
```


Q086 whose genes are located in the region 2p12 to 2p24.2


```
#time: 0.15
select distinct ?entry where {
  ?entry :gene  ?gene .
  ?gene :chromosome "2"^^xsd:string .
  ?gene :band ?band .
  filter (?band >= "p12"@en && ?band <= "p24.2"@en )
}
```


QTerm001 - Terms of controlled vocabularies containing some word(s)


```
SELECT DISTINCT * WHERE { 
  ?term rdfs:label ?label ; a ?type .
  # ---------------------------
  # exact match
  # ---------------------------  
   filter(?label = "peroxisome"^^xsd:string)
  
  # ---------------------------
  # starting with peroxisome
  # --------------------------- 
  # filter(regex(?label,"^peroxisome"))
  
  # ---------------------------
  # containing peroxisome
  # ---------------------------
  #filter(regex(?label,"peroxisome"))
  
  # ------------------------------------
  # containing peroxisome and receptor 
  # ------------------------------------
  #filter(regex(?label,"peroxisome.*receptor"))
} LIMIT 20
```


