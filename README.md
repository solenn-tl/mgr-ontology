# MGR Ontology

This repository contains the documentation and RDF implementation of the Music Graph RAG ontology devoted to the representation of music talks and associated knowledge that should be usable for semantic retrieval tasks.

## Methodology and validation
* Ontology has been developped using the [SAMOD methodology](https://essepuntato.it/samod/) and tested with the [Philharmonie de Paris - Cité de la Musique talks](https://pad.philharmoniedeparis.fr/), recordings, transcript and metadata.
* The MGR ontology reuses concepts and properties of:
    * [Schema.org](https://schema.org/) ontology
    * [Dublin Core DCMI Metadata Terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/) ontology (DCTERMS)
    * [Prov-O](https://www.w3.org/TR/prov-o/) ontology
    * [Time](https://www.w3.org/TR/owl-time/) ontology
* Audio excerpts URL are build following the [W3C Media Fragments Enforcement](https://www.w3.org/TR/media-frags/) guidelines.
* The ontology consistency has been validated in [Protégé](https://protege.stanford.edu/) with HermiT reasonner and with Ooops! (TODO -> down currently).
* Annotation properties have been checked with [Mentor](https://mentor-vscode.dev/).
* Final documentation is generated with [Widoco](https://dgarijo.github.io/Widoco/doc/tutorial/#widoco_intro).
* Gemini Auto model has been use to correct typos and improve formulation in french and english. The ontology developement has been performed by the authors.
* Further developpement may validate and extend the ontology with other general audience talks.

## SAMOD documentation (```nl-doc``` folder)
*For each module, a motivation scenario (`_scenario.md`), a list of competency questions (`_cq.md`), a glossary (`_glossary.md`) and examples of RDF implementations with a chart (`_to_rdf.md`) are provided.*
* The ```Talk``` module aims to describe talks independently from its recorded/derived versions (video, audio, associated transcript). It focuses on the questions <i>Who? What? When? Where?</i>
* The ```Recording``` module aims to described audio or video realization of a talk and associated excerpts.  
* The ```Transcript``` module aims to structure the textual version of a talk/recording. The module also include talk parts that can follow various splitting/chunking strategies.
* The ```Entities``` module aims to decribe the main type of entities that may be retrieved or associated with the conferences: persons, work of art, places, organizations, musical terms, historical events etc. 
* The ```Activity``` module is devotated to the sourcing of the informations added to the KG (how they have been provided etc.). 
* The ```Retrieval``` module aims to facilitate the use of the knowledge graph for chunk level retrieval process (shortcut properties etc.).

## Ontology implementation (```ontology``` folder)
The ontology has been natively developped in Turtle format.
The folder also contains SHACL rules that helps checking the KG consistency.

## Widoco doc (```docs``` folder)
This folder contains the documentation of the ontology generated with Widoco using the `.ttl` file in ```ontology``` folder.

## KG construction (```script``` folder)
TBA

### Metadata-based construction
* Talks
* Recordings
* Transcript (ASR-splitting)
    * One named graph per chunking strategy

### Entities
* A knowledge base of Persons and Work of Arts is maintained by the Philharmonie. We use it to initiate a referential of candidates for entity linking. We perform linking between them and other KGS like Wikidata and DOREMUS (already built with data from Bnf, Philharmonie and Radio France). 

## References
* Peroni SAMOD
* DOREMUS paper
* G-Reasoner Paper
* W3C Media Fragments Enforcement

## Acknowledgement
The Music Graph RAG project is a collaboration between the Philharmonie de Paris - Cité de la Musique (French Ministry of Culture) and Inria.

## How to cite
```bib
```