The neXtProt function prediction dataset released in June 2023, containing [manually verified predictions for 239 uncharacterized proteins](https://www.nextprot.org/about/functional-proteome-project) was successfully used to test DeepGO-SE, a new AI-based tool predicting protein functions developed by KAUST bioinformatics researcher Maxat Kulmanov and his colleagues.


Kulmanov M, Guzmán-Vega FJ, Duek Roggli P, Lane L, Arold ST, Hoehndorf R. Protein function prediction as approximate semantic entailment. Nat Mach Intell. (2024). [doi: 10.1038/s42256-024-00795-w](https://doi:10.1038/s42256-024-00795-w)

##Abstract

The Gene Ontology (GO) is a formal, axiomatic theory with over 100,000 axioms that describe the molecular functions, biological processes and cellular locations of proteins in three subontologies. Predicting the functions of proteins using the GO requires both learning and reasoning capabilities in order to maintain consistency and exploit the background knowledge in the GO. Many methods have been developed to automatically predict protein functions, but effectively exploiting all the axioms in the GO for knowledge-enhanced learning has remained a challenge. We have developed DeepGO-SE, a method that predicts GO functions from protein sequences using a pretrained large language model. DeepGO-SE generates multiple approximate models of GO, and a neural network predicts the truth values of statements about protein functions in these approximate models. We aggregate the truth values over multiple models so that DeepGO-SE approximates semantic entailment when predicting protein functions. We show, using several benchmarks, that the approach effectively exploits background knowledge in the GO and improves protein function prediction compared to state-of-the-art methods.


