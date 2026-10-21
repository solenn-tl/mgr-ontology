# Talks Ontology
The ontology contains 7 submodules :
- Events
- Recordings
- Metadata
- Entities
- Transcripts
- Activities
- Retrieval

## Overview
```mermaid
flowchart TD
    A(<b>Recording</b><br>+syracuse_id<br>+documentId<br>+fileURL<br>+date<br>+duration:time)
    B(Transcript)
    C(<b>RecordingType</b><br>Audio,Video)
    D(Activity)
    E(<b>Person</b><br>+lastName:str<br>+firstName:str<br>)
    F(<b>Speaker</b><br>+role:str)
    G(<b>RecordingPart</b><br>+title<br>+startTime:time<br>+endTime:time<br>+duration:time)
    H(<b>TranscriptPart</b><br>+text:str<br>+startTime:time<br>+endTime:time<br>+language:str)
    I(Keyword)
    J(Event)
    K(EventSet)
    L(EventType)
    M(<b>RecordingPartType</b><br>Chapter,Excerpt,Turn)
    P(<b>Entity</b>)
    R(Location)
    S(Organization)
    T(WorkOfArt)
    U(MusicalTerm)
    V(Date)
    W(Event)
    X(Misc)
    Y(<b>EntityUtterance</b><br>+span:str<br>+label:str<br>+starChar:int<br>+endChar:int<br>+confidenceScore:str<br>+provider:str)
    Z(Document)

    A -- hasDerivedVersion --> B
    A -- hasRecordingType --> C
    A -- hasPart --> G
    M -- owl:subclassOf --> G
    B -- prov:wasGeneratedBy --> D
    B -- hasPart --> H
    F -- speaksIn --> A
    F -- speaksIn --> M
    F -- speaksIn --> G
    F -- owl:subclassOf --> E
    A -- isDescribedbyKeyword --> I
    A -- isRecordingOf --> J
    J -- isEventType --> L
    J -- isPartOf --> K
    K -- isEventType --> L
    E -- owl:subclassOf --> P
    R -- owl:subclassOf --> P
    S -- owl:subclassOf --> P
    T -- owl:subclassOf --> P
    U -- owl:subclassOf --> P
    V -- owl:subclassOf --> P
    W -- owl:subclassOf --> P
    X -- owl:subclassOf --> P
    H <-- correspondsTo --> G
    H -- mentions --> P
    P -- <i>openIErelation</i>(superproperty) --> P
    G -- hasPart --> G
    G -- isRecordingPartType --> M
    I <-- isRelatedTo --> P
    Y -- isManifestationOf --> P
    Y -- recognizedIn --> H
    H -- hasPart --> H
    Z -- owl:subclassOf --> A
    Z -- owl:subclassOf --> B

classDef recording fill:#5CD660,stroke:#29592B,color:#111827
class A,C,G,M,Q,N recording
classDef metadata fill:#25A0E8,stroke:#17226E,color:#111827
class F,I metadata
classDef event fill:#CC8D25,stroke:#755115,color:#111827
class J,K,L event
classDef structure fill:#E34E30,stroke:#8A3120,color:#111827
class D activity
classDef derived fill:#A045E6,stroke:#492069,color:#111827
class B,H,Y derived
classDef entity fill:#DE6DD9,stroke:#8A3286,color:#111827
class E,P,R,S,T,U,V,W,X entity
```

### Event
The event submodule describes ```Event``` elemnts organised by the an institution.
One event may lead to one ```Recording```. An event may be a part of a serie of events (```EventSet```) that may correspond to a season, an exhibition, a serial conference, etc which don't have a direct recording.
An event is set at a given date and place. 
It may have a certain type (keynote, commented concert etc).

### Recording
The recording submodule describes recordings (audio or video) of a given ```Event```. A recording has a duration, a date and place of recording. It can have derived version (vidoe derived to audio, audio tracks turn to text, etc.). 

### Metadata
Metadata is used to describes both ```Event``` and ```Recordings```. 
They include ```Speaker``` (someone who speak in an event) and ```Keyword``` (a taxonomy is maintained by librarians).

### Transcript
The transcript submodule refers to a derived, textual, version of a recording. 
A 
Each ```Recording``` has an equivalent ```Transcript``` item. 
Of course, ```RecordingPart``` is associated to a segment of that transcript (```TranscriptPart```).

### Entity
An entity can be associated with unique identifiers from external knowledge based (Wikidata, DOREMUS etc.).
Several subclasses have been defined : 
* ```Person```: a natural person. 
     * May have one or many activities (composer, moviemaker etc.)
     * May have created or played certain ```WorkOfArt```
     * Related to certain ```Location``` or ```Organization```
     * Related to certain ```Date``` or ```Event```
* ```MusicalTerm``` : music style, instrument, 
* ```WorkOfArt``` : name of a work of art, several domains are considered (music, cinema, litterature, painting) that may be mentionned in the conferences.
* ```Location``` : a named place
* ```Organization``` : an organization may be a political regime, a cultural institution (museuem) or association
* ```Date``` : a date is a temporal reference, that is an instant (numbered day in a month, a year, a century) or an interval (between two yeares etc.). 
* ```Event``` : an event refers to a dated instant or time interval. It can be an historical event or a cultural event mentionned in a conference.
* ```Miscellanous``` : any other relevant entity mentionned in documents

### Activity
An activity is a manual or automated process that lead to the creation of a resource (Transcript, Entity, Relation).

### Retrieval
This module aims to make the knowledge graph usable for semantic retrieval approaches. 