# Transcript module - Scenario

A **transcript** is a derived, textual version of a recording part that captures a talk part. It can be generated manually or automatically using an automated speech recognition tool (ASR).
Transcripts may also include speaker diarization.
Synchronization between audio spans (time) and text is mandatory.

A transcript is an aggregation of transcript parts splitted following a certain strategy.
* *Talk identifier* (mandatory): has a relation with the corresponding Talk
* *Recording identifier* (mandatory): has a relation with the corresponding Recording
* an **identifier** (mandatory)
* an **activity** (mandatory): how the text has been provided
* an **aggregation strategy** (mandatory): how the associated transcript parts have been splitted
* 1..n **transcripts parts** (mandatory)

A transcript part is an elementary part of the transcription of a recorded talk, aligned with the recording part (and time).
* **segment/chunk identifier** (mandatory)
* **segment/chunk order** in a full transcript splitted with a given strategy (mandatory)
* **chunking process**: how the chunk have been produced (e.g. `ASR sentence`, `Chunking strategy A`, etc. mandatory)
* **text value** (mandatory)
* **transcription score** (optionnal)
* **start time of associated recording part** (mandatory)
* **end time of associated recording part** (mandatory)
* **ASR speakers**: unvalidated speaker.s ids automatically generated (optionnal)

## Examples

### Example 1: transcript element
* `Talk` syracuse_id: 758797
* `Recording` syracuse_id: 758797
* **Transcript** :
    * TranscriptPart(*Il y a eu une autre influence en dehors...*)
    * TranscriptPart(*Et j'entends non seulement de Malarmé...*)
    * ...
* **Chunking process**: `ASR sentence`
* **Provided by**: WhisperX_activity_datetime

### Example 2: sentence level transcript
*The sentence level is a typical output level for any kind of transcript process (manuall or ASR).*

* related `Transcript`(ASR sentence) element
* **Segment identifier:** uuid
* **Chunk order**: 1
* **Text**: *Il y a eu une autre influence en dehors d'une influence picturale comme celle de Clé, c'est celle de Malarmé. les images ordinaires, en mettant l'évidence visible en déroute ?* (mandatory)
* **Score**: *mean of word level transcript*
* **Start time in recording part**: 0.52 (seconds) (mandatory)
* **End time in recording part**: 6.909 (seconds) (mandatory)
* **ASR Speakers**: SPEAKER_01

### Example 3: group of sentence transcript
*The group of sentences level is a balanced splitting for retrieval process. Aggregation may be performed according several strategies (structure-based chunking, semantic-based chunking, discourse processing etc.)*

* related `Transcript`(Chunking process A) element
* **Segment identifier:** uuid
* **Chunk order**: 1
* **Text**: *Il y a eu une autre influence en dehors d'une influence picturale comme celle de Clé, c'est celle de Malarmé. les images ordinaires, en mettant l'évidence visible en déroute ?
Et j'entends non seulement de Malarmé dans son poème, qui l'a exprimé directement dans ses poèmes, mais aussi dans la structure de ses poèmes, dans la structure mentale, dans sa conception de la poésie qui est vraiment une des conceptions les plus extraordinaires qui, à mon avis, est existée.*
* **Score**: *mean of word level transcript*
* **Start time in recording part**: 0.52 (seconds) (mandatory)
* **End time in recording part**: 6.909 (seconds) (mandatory)
* **ASR Speakers**: SPEAKER_01

## Notes
* Use the Open Annotation Data Model (OA / Web Annotation) to map text segment with recording parts.