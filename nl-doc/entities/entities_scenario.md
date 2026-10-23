# Entities module - Scenario

## Description
The **entities** module aims to describe the main type of entities that may be mentionned in the metadata and in the talks.
We distinguished 7 main types of entities that have their own properties. 

Based on the Philharmonie de Paris - Cité de la Musique talks, we lists the following types, grouped in two categories: common entity types and domain-specific entity types.

### Common entity types
#### Person 
* include artists but not only. May be described with lastname, firstname, birthname, nickname, birth date, place of birth, occupation, etc.
* The Philharmonie has a referential of persons. In it they, are described with the following properties:
    * a **syracuse_id** (*mandatory*)
    * a **document_id**  (*optionnal*, observed in certain metadata files of the talks)
    * a **reference label** in the form of {{NAME}}, {{FIRSTNAME}} {{DATES}} (*mandatory*, *last two parameters are optionnal*)
    * a **number of documents related to that person in Philharmonie system** (*optionnal*)
    * a **genre** (*optionnal, a: men, b: woman*)
    * an **ISNI (International Standard Name Identifier)** (*optionnal*), [very usefull for entity linking](https://www.bnf.fr/fr/isni-international-standard-name-identifier)
    * a **BnF FRBNF identifier** (*optionnal*), very usefull for entity linking
    * a **comment** (*optionnal*)
    * **alternate labels** (*optionnal*)
    * **not accepted alternate labels** (*optionnal*)
    * a **role** (*optionnal*, observed in certain metadata files of the talks)

#### Place 
* It may include building, city, region, country, continent, etc.
* A place may be described by name, location (geographical coordinates), spatial relations with other entities (city is in a country etc.)

The Philharmonie thesaurus contains a wide variety of places instances that are already strutured into a hierarchy (top entity: DESC1160884, Aire géographique). They are described with: 
* a **syracuse_id** (*mandatory*)
* a **label** (*mandatory*)

Hierarchy in the thesaurus is not one type per level!
```
Aire géographique
|-> Continent 
    |-> Country OR Area
         |-> Country, Region etc.
```

#### Organization
* It includes cultural institution, museum, political regime etc.
* An organization may be described by a name, a type of organisation, a date of creation etc.

The Philharmonie thesaurus contains a range of organization instales bellow the `Conservation -> Collection` group of keywords (`DESC155435 -> DESC145290`). They are described with: 
* a **syracuse_id** (*mandatory*)
* a **label** (*mandatory*)

#### Event
* It includes historical period and events (as Middle Age, World War II, etc.) but also precise cultural events set are certain dates (ex: Summer festival 2009, season 2004-2005).

The Philharmonie thesaurus contains a range of historical periods bellow the `Histoire -> Période historique` group of keywords (`DESC145865 -> DESC145864`). They are described with: 
* a **syracuse_id** (*mandatory*)
* a **label** (*mandatory*)

#### Date
* A date is a temporal reference. In our case, we are only interested by deterministic temporal references that include a year or century (day+month+year, month+year, year, century etc.)

### Domain-specific entity types:
#### Work of Art
* This type of entities correspond to create works: musical work and also works from other artistic fields (cinema, painting, etc.). It is described by:
    * a **title**
    * a **nature**
    * an **artistic domain**
    * a **date/period of creation*
    * an **author**
    * a **description**
    ...
* Musical works are the most important category of works in the MGR project. They are described with additionnal properties.
* The Philharmonie de Paris owns an extensive refrential of musical works. Works are described with:
    * a **syracuse_Id**
    * a **preferred label**
    * an **author**
    * a **date**
    * an **opus number**
    * a **catalog number**
    * a **key**
    * Lien autorité (70x) pour OEX
    * some notes about:
        * **note about opus number**
        * **note about the key**

#### Music Term
* Any  vocabulary element who refers to the music domain. For example: instruments, style, tool etc. They may be described by:
    * a **label**
    * a **type of term**
    * a **creator**
    * a **date of creation**
    * a **period of use**

* The Philharmonie thesaurus contains music terms:
    * instruments: `Instrument de musique (DESC155964)`
    * part of instruments: `Instrument de musique (élément) (DESC145780)`
    * music style: `Art -> Musique -> Genre musical (DESC144952 -> DESC144958 -> DESC67193)` and `Style musical (DESC68608)`
    * creation of instruments: `Facture instrumentale -> Matériau (DESC155527 -> DESC155547)`
    * tools: `Facture instrumentale -> Outil (DESC155527 -> DESC155554)`

## Examples (1): In metadata
*We observe that personnes can be described differently in the metadata, between keys but also bellow a same key.*
### Example 1.1: person (1)
*Example retrieved in the people key of metadata of a talk*
* Talk(1140650) :
* Person syracuse_id : 54229
* Person documentId : y80cndhqpm8mo9pbyeiwrkuu
* First name: Olivier
* Last name: Baumont

*Other version in the metadata of the same talk in the speakers key*
* Talk(1140650) :
* Value: *Olivier Baumont, claveciniste, professeur au Conservatoire national supérieur de musique et de danse de Paris - CNSMDP, Paris*

## Examples (2): In talks
### Example 2.1: person
* Talk(758797): *Concert donné à l'occasion du 80ème anniversaire de Pierre Boulez*
* Chunk(1) : *Il y a eu une autre influence en dehors d'une influence picturale comme celle de Clé, c'est celle de Malarmé.*
* Person(1):
    * **Span**: "Clé"
    * **Refers to**: Paul Klee (Q44007), german-swiss artiste (1879–1940)
* Person(2)
    * **Span**: "Malarmé"
    * **Refers to**: Stéphane Mallarmé (Q767), french poet (1842–1898)

## Notes
* These entities interact, in the discourse context (Talk) and in the real world context (External knowledge). Some interesting interactions that a user may refers to in a query may not be provided in the context of a talk as the speaker assumes the audience know the information.
    * Relations between entities **in the text** may be discovered using openIE approaches and added as an extension to the MGR  ontology.
    * Relations between entities that already exists in external knownledge bases may be added to the MGR classes and the associated properties added in an extension of the MGR ontology.
* It would be relevant to link the thesaurus with other KG and ontologies as its keyword are used a lot in the metadata.