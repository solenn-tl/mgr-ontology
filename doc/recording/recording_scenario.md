# Recording module - Scenario

A **recording** is a video or audio realisation that fix a record of a talk or event. 
It may be cutted into parts following several strategies (hierarchical or not, interconnected or not). 
It can have derived versions: 
- audio track of a video
- transcript of an audio track (see `Transcript` module).

A recording is described by:
* an associated talk (mandatory)
* a `type` (audio, video; mandatory)
* a `notice_type` (Philharmonie specific property about file type, optionnal)
* a `format` (mp3, mp4, etc.; mandatory)
* a `duration` (with a certain unit; mandatory)
* a `file URL` (if available online; optional)
* a `director` (optionnal) who is in charge of the recording and/or of the editing

A recording part is described by:
* a top level recording
* identifiers
* a `notice_type` (Philharmonie specific property about file type, optionnal)
* a `start` time stamp in the complete recording (mandatory)
* a `end` time stamp in the complete recording (mandatory)
* a `title` (optional)
* a `summary` (optional)
* a `file URL` that makes the user able to start the full recording file at the good start time stamp (optional)

Excerpts that we aim to return to the user are recording parts. Not all recordings parts are excerpts (for example a long chapter is not excerpt).

## Examples

### Example 1: recording of a talk
* **Talk identifiers**:
    * Syracuse_id: 998308
    * Document_Id: kjskn1xyifa881izhun6ou3w
* **Recording identifiers**:
    * **URI**: CMAU000171000
* **Notice type**: MPA1
* **Type**: audio
* **Format**:
    * **Audio format**: mp3
* **Duration**: 7324.17 (seconds)
* **File URL**: https://cdn.philharmoniedeparis.fr/http/conferences/merged/CMAU000171000_merged.mp3
* **Recording part URL**: *Not provided*

### Example 2: recording part (1)
* **Talk identifiers**:
    * Syracuse_id: 998308
    * Document_Id: kjskn1xyifa881izhun6ou3w
* **Talk part identifiers**:
    * Syracuse_id: 1030796
    * Document_Id: dxwe0o8wnq798kn9hhmve7vn
* **Notice type**: MPA2
* **Type**: audio
* **Format**:
    * **Audio format**: mp3
* **Duration**: 681.98 (seconds)
* **Start time in recording file**: 0 (seconds)
* **End time in recording file**: 681.98 (seconds)
* **File URL**: https://cdn.philharmoniedeparis.fr/http/conferences/merged/CMAU000171000_merged.mp3#t=0,681.98

### Example 3: recording part (2)
* **Talk identifiers**:
    * Syracuse_id: 998308
    * Document_Id: kjskn1xyifa881izhun6ou3w
* **Talk part identifiers**:
    * Syracuse_id: 1030796
    * Document_Id: dxwe0o8wnq798kn9hhmve7vn
* **Notice type**: MPA2
* **Type**: audio
* **Format**:
    * **Audio format**: mp3
* **Duration**: 2358.27 (seconds)
* **Start time in recording file**: 681.98 (seconds)
* **End time in recording file**: 3040.25 (seconds)
* **File URL**: https://cdn.philharmoniedeparis.fr/http/conferences/merged/CMAU000171000_merged.mp3#t=681.98,3040.25

## Notes
* We use the `W3C Media Fragments URI 1.0` conventions for file url of recording parts.
* In the case of the Philharmonie de Paris, some recording parts have already been annotated by librarians and have a notice and syracuse_id. We will have to create new parts for retrieval that should be identified by a graph-local id.