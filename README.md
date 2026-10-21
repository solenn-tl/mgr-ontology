# MGR Ontology

This repository contains the documentation and RDF implementation of the Music Graph RAG ontology devoted to the representation of music talks and associated knowledge that should be usable for semantic retrieval tasks.

Ontology has been developped using the SAMOD methodology and tested with the Philharmonie de Paris - Cité de la Musique talks.

Further developpement may validate and extend the ontology with other general audience talks.

## Documentation (```doc``` folder)
* The ```Talk``` module aims to describe talks independently from its recorded versions (video, audio, associated transcript). It focuses on the questions <i>Who? What? When? Where?</i>
* The ```Recording``` module aims to described audio or video realization of a talk and associated excerpts.  
* The ```Transcript``` module aims to structure the textual version of audio/video recording. The module also include struring of the talk based on several transcript splitting.
* The ```Entities``` module aims to decribe the main type of entities that may be retrieved or associated with the conferences: persons, places, organizations, musical terms, work of art, historical events etc. 
* The ```Activity``` module is devotated to the sourcing of the informations in the KG, including representation of the automated process using to structure knowledge from the recordings and transcripts.
* The ```Retrieval``` module aims to facilitate the use of the knowledge graph in chunk level retrieval process.