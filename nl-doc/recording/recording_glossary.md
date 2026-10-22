# Recording module - Glossary

| Term (English / Français) | Category | Definition / Description |
| --- | --- | --- |
| **Recording / Enregistrement** | Class | A video or audio realization that fixes a record of a talk or event. Subclass of `schema:MediaObject`. |
| **Recording Part / Partie d'enregistrement** | Class | A segment or excerpt of a top-level recording (such as a chapter or slice used for retrieval). Subclass of `schema:MediaObject`. |
| **is recording of / est l'enregistrement de** | Object Property | Relates a recording to the talk it captures (`mgr:Talk`). |
| **has recording part / a pour partie d'enregistrement** | Object Property | Relates a top-level recording to one of its segments or parts (`mgr:RecordingPart`). |
| **is part of recording / fait partie de l'enregistrement** | Object Property | Relates a recording part back to its parent top-level recording. |
| **depicts talk part / illustre la partie de conférence** | Object Property | Connects a recording part to the intellectual discourse segment (`mgr:TalkPart`) it captures. |
| **has director / a pour réalisateur** | Object Property | Relates a recording to the person in charge of recording and/or editing (`schema:Person`). |
| **is director of / est le réalisateur de** | Object Property | Relates a person to the recording they directed. |
| **notice type / type de notice** | Datatype Property | Philharmonie-specific metadata property about the file notice type (e.g., MPA1, MPA2). |
| **recording type / type d'enregistrement** | Datatype Property | The general media type, such as audio or video. |
| **media format / format du média** | Datatype Property | The specific technical format of the video or audio track (e.g., mp3, mp4, wav). |
| **start time / temps de début** | Datatype Property | Start timestamp in seconds relative to the full recording file (`xsd:decimal`). |
| **end time / temps de fin** | Datatype Property | End timestamp in seconds relative to the full recording file (`xsd:decimal`). |