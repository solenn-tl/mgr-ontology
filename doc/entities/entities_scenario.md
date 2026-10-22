# Entities module - Scenario

## Description
The **entities** module aims to describe the main type of entities that may be mentionned in the metadata and in the talks.
We distinguished 7 main types of entities that have their own properties. 

Based on the Philharmonie de Paris - Cité de la Musique talks, we lists the following types, grouped in two categories: common entity types and domain-specific entity types.

Common entity types:
* **Person**: include artists but not only
    * lastname, firstname, birthname, nickname, birth date, place of birth, occupation, etc.
* **Place**: city, country, building, continent
    * name, location (geographical coordinates), spatial relations with other entities (city is in a country etc)
* **Organization**: cultural institution, museum, political regime etc.
    * name, type of organisation
* **Date**: day+month, month+year, year, century etc.
* **Event**: mainly historical event or period
    * label, date, type

Domain-specific entity types:
* **Work of Art**: main focus on musical work but may include works from other artistic fields (cinema, painting)
    * name, nature, domain, date of creation, author, description ...
* **Music Term**: music specific vocab like instrument, music style
    * name, nature, date of creation, period of use, description, ...

These entities interact, in the discourse context (Talk) and in the real world context (External knowledge). 
Some interesting interactions that a user may refers to in a query may not be provided in the context of a talk as the speaker assumes the audience know the information.

## Examples (1): In metadata

### Example 1.1: person (speaker)

### Example 1.2: person (subject of talk)

### Example 1.3: place

### Example 1.4: organization

## Examples (2): In talks