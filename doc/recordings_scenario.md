# Recordings

A **recording** is a video or audio representation of an event. It's the result of a continuous or uncontinous recording activity that have resulted in the production of a consistent content at the disposal of users.

A recording is described by:
* a ```type``` (audio, video; mandatory)
* a ```format``` (mp3, mp4, etc.; mandatory)
* a ```duration``` (with a certain unit; mandatory)
* a ```file URL``` (if available online; optional)
* a ```homepage URL``` on user plateforme (if available online; optional)
* a ```director``` whos is in charge of the recording and/or of the editing

A recording is associated with an ```Event``` which is a conference/talk. 
The recording may have 1..n subparts (chapters, tracks). 
It can have derived versions (audio only of a video, transcript of an audio/video, etc.).

### Competency question
* What is the type of the initial recording of talk X ?
>>> Audio

* Return the list of video recordings.
>>> List of recordings whose format is a video.

* Return the list of recordings under 1 hour.
>>> List of recordings whose duration is under 1 hour.

* Return the chronological list of subparts of conference X with it's timestamps.
>>> List of recording fragments.