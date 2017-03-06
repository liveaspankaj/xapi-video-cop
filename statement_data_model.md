WORK IN PROGRESS: This document is a work in progress and may contain incomplete or inaccurate information. 


#2. xAPI Statement Data Model


##2.1 Statement ID

The LRP MUST assign a statement id property in UUID format (as defined in the xAPI specification) for all statements it issues.


##2.2 Actor

The Actor property must be defined as per the xAPI Specification. 

When the video is launched in an LMS, Actor must be provided by the LMS. 

##2.3 Verbs

The following xAPI verbs are defined in this specification.

LRP MUST use the below verbs that are indicated as mandatory in other sections of this specification.

<a name="verbs_initialized"></a>
###2.3.1 Initialized
<table>
<tr><th align="left">Verb</th><td>Initialized</td></tr>
<tr><th align="left">ID</th><td>http://adlnet.gov/expapi/verbs/initialized</td></tr>
<tr><th align="left">Description</th><td>An "Initialized" statement is used by the LRP to indicate that the video has been fully initialized or launched.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>The LRP MUST use "Initialized" in the first statement in the video session.  The LRP MUST NOT issue multiple statements with "Initialized" for the same video session.</td></tr>
<tr><th align="left">Usage</th><td>An "Initialized" statement is used by the LRP to indicate that the video has been fully initialized or launched.</td></tr>
</table>


<a name="verbs_played"></a>
###2.3.2 Played
<table>
<tr><th align="left">Verb</th><td>Played</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/verbs/played</td></tr>
<tr><th align="left">Description</th><td>Indicates that the actor started experiencing the recorded media object.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>The LRP MUST use "Played" when the actor starts experiencing the media.</td></tr>
<tr><th align="left">Usage</th><td>Used when the actor generally played a video or clicked the play button. Also used when the video starts after an actor seeked to a new position in video.</td></tr>
</table>

<a name="verbs_paused"></a>
###2.3.3 Paused
<table>
<tr><th align="left">Verb</th><td>Paused</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/verbs/paused</td></tr>
<tr><th align="left">Description</th><td>Indicates that the actor temporary or permanently stopped experiencing the recorded media object.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>The LRP MUST use "Paused" when the media is stopped. A paused statement MUST be sent before a terminated or abandoned statement if not already sent.</td></tr>
<tr><th align="left">Usage</th><td>Indicates that the actor temporary or permanently stopped experiencing the recorded media object.</td></tr>
</table>

<a name="verbs_seeked"></a>
###2.3.4 Seeked
<table>
<tr><th align="left">Verb</th><td>Seeked</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/verbs/seeked</td></tr>
<tr><th align="left">Description</th><td>Indicates the actor changed the progress towards a specific point.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>The LRP MUST use "Seeked" when the Actor moves the progress bar forward or backward to a specific time in video.</td></tr>
<tr><th align="left">Usage</th><td>Used in combination with time-from and time-to extensions when the Actor moves the progress bar forward or backward to a specific time in the video.</td></tr>
</table>

<a name="verbs_interacted"></a>
###2.3.5 Interacted
<table>
<tr><th align="left">Verb</th><td>Interacted</td></tr>
<tr><th align="left">ID</th><td>http://adlnet.gov/expapi/verbs/interacted</td></tr>
<tr><th align="left">Description</th><td>Used to express that the actor interacted with the player (except play, pause, seek). e.g. mute, unmute, change resolution, change player size, etc.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional</td></tr>
<tr><th align="left">Usage</th><td>Used to express that the actor interacted with the player (except play, pause, seek). e.g. mute, unmute, change resolution, change player size, etc.</td></tr>
</table>


<a name="verbs_completed"></a>
###2.3.6 Completed
<table>
<tr><th align="left">Verb</th><td>Completed</td></tr>
<tr><th align="left">ID</th><td>http://adlnet.gov/expapi/verbs/completed</td></tr>
<tr><th align="left">Description</th><td>Used to express that the actor completed a video by watching all parts of the video at least once.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>The LRP MUST use "Completed" when the Actor has completed a video by watching all parts of the video at least once.<br>
The "success" property of the result MUST be set to true for this statement.<br>
The "duration" property of the result MUST be included in this statement and MUST represent total time spent during consuming the video under current registration. e.g. P218S

</td></tr>
<tr><th align="left">Usage</th><td>Used to express that the actor completed a video by watching all parts of the video at least once. The progress and heatmap result extension can be used to calculate the duration and completion of video.</td></tr>
</table>

<a name="verbs_terminated"></a>
###2.3.7 Terminated
<table>
<tr><th align="left">Verb</th><td>Terminated</td></tr>
<tr><th align="left">ID</th><td>http://adlnet.gov/expapi/verbs/terminated</td></tr>
<tr><th align="left">Description</th><td>Used to express that the actor ended a video.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional. 
<ul>
<li>The LRP MAY use "Terminated" when the Actor has terminated the video. </li>
<li>A "Paused" statement MUST before sent before "Terminated" statement if not already sent.</li>
<li>Any statements after this in the current video session MUST NOT be sent, and will be ignored if sent.</li>
</ul>

</ul>
</td></tr>
<tr><th align="left">Usage</th><td>Used to express that the actor ended a video. </td></tr>
</table>

<a name="verbs_abandoned"></a>
###2.3.8 Abandoned
<table>
<tr><th align="left">Verb</th><td>Abandoned</td></tr>
<tr><th align="left">ID</th><td>http://adlnet.gov/expapi/verbs/abandoned</td></tr>
<tr><th align="left">Description</th><td>Used to express that the activity provider was able to determine that the session was terminated, however,a terminated statement was not received due to a failure.</td></tr>
<tr><th align="left" nowrap>LRP/LRS/LMS Obligations</th><td>Optional.
<ul>
<li>The LRP, LRS or LMS MAY use "Abandoned" when it is determined that the session was terminated, however,a terminated statement was not received due to a failure. </li>
<li>A "Paused" statement MUST before sent before "Abandoned" statement if not already sent.</li>
<li>Any statements after this in the current video session MUST NOT be sent, and will be ignored if sent.</li>
</ul>
</td></tr>
<tr><th align="left">Usage</th><td>Used to express that the activity provider was able to determine that the session was terminated, however,a terminated statement was not received due to a failure.</td></tr>
</table>

##2.4 Object

An Object with objectType "Activity" MUST be present, as specified in the xAPI Spec.

The Object represents the video or media being consumed by the Actor.  

###2.4.1 Definition

Object definition MAY contain name, description and other details of the media, as per the xAPI Spec. 

Object definition MUST be present and MUST contain activity "type" as: https://w3id.org/xapi/video/activity-type/video



##2.5 Result

Result is an optional property that represents a measured outcome related to the Statement in which it is included.

It may be present in a statement depending on the verb used.

###2.5.1 Score

A score is not required to be reported. If a score is reported, it must be as per the xAPI Spec. 

###2.5.2 Success

The "success" property of the result MUST be set to true for the 'completed' statement. 

Other Video Profile statements MUST NOT include the "success" property.

###2.5.3 Completion

The "completion" property of the result MUST be set to true for the 'completed' statement. 

Other Video Profile statements MUST NOT include the "completion" property.

###2.5.4 Duration

The "duration" property is an ISO 8601 formatted time value. 

Duration MUST be included in "completed" statement and MUST represent total time spent consuming the video under current registration. e.g. P218S

###2.5.5 Result Extensions

There are several additional results related values defined in Video Profile that can be added to the statement under result extensions. 

###2.5.5.1 Time

<table>
<tr><th align="left">Extension</th><td>time
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/time</td></tr>
<tr><th align="left">Description</th><td>Used to express the time into the video.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>The LRP MUST assign time value to statements with "played", "paused", "terminated", "interacted" and "completed" verbs.</li>
<li>Float Value with maximum 3 decimals.</li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td>Example: "23.560" represents video position at 23 seconds and 560 milliseconds.</td></tr>
</table>

###2.5.5.2 Time From

<table>
<tr><th align="left">Extension</th><td>time-from
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/time-from</td></tr>
<tr><th align="left">Description</th><td>Used to identify the point in time the actor changed from in a media object during a seek operation.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>The LRP MUST assign time-from value to statements with "seeked" verbs only.</li>
<li>Float Value with maximum 3 decimals.</li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td>Example: "23.560" represents video position at 23 seconds and 560 milliseconds.</td></tr>
</table>

###2.5.5.3 Time To

<table>
<tr><th align="left">Extension</th><td>time-to
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/time-from</td></tr>
<tr><th align="left">Description</th><td>Used to identify the point in time the actor changed to in a media object during a seek operation.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>The LRP MUST assign time-to value to statements with "seeked" verbs only.</li>
<li>Float Value with maximum 3 decimals.</li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td>Example: "23.560" represents video position at 23 seconds and 560 milliseconds.</td></tr>
</table>


###2.5.5.4 Progress

<table>
<tr><th align="left">Extension</th><td>progress
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/progress</td></tr>
<tr><th align="left">Description</th><td>Used to expresses the percentage of media consumed by the actor.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>The LRP MUST assign progress value to statements with "paused", "terminated" and "completed" verbs.</li>
<li>The LRP MAY assign progress value to other statements.</li>
<li>Value is a decimal between 0.0 and 1.0.</li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td>The progress value includes all attempts made during the current registration. </td></tr>
</table>

###2.5.5.5 Heat Map Value


<table>
<tr><th align="left">Extension</th><td>heat-map
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/heat-map</td></tr>
<tr><th align="left">Description</th><td>Heat map data showing parts of the video the actor watched during current registration in chronological order.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>The LRP MUST assign heat-map value to statements with "paused", "terminated" and "completed" verbs.</li>
<li>The LRP MAY assign heat-map value to other statements.</li>
<li>Value is a string. Each part of the video watched is separated with [,]. The 'Time From' and 'Time To' values are separated with [.].</li> 
<li>The time values must match the values recorded as time, time-to and time-from in played, paused, seeked statements.</li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td>The heat-map value includes all attempts made during the current registration. <br>Example:  0.000[.]12.000[,]14.000[.]21.000[,]18.000[.]30.000</td></tr>
</table>


##2.6 Context

All Video Profile statements MUST contain a context that includes all objects/values as defined in this section.  

###2.6.1 Registration

The value for the registration property used in the context object MAY be the value provided by the LMS via the launch URL. If registration is not provided via the launch mechanism, the LRP MAY set a fixed registration value.

The registration value is important because the "progress", the "heat-map" value and "completion" is based on aggregate of all attempts with same registration value attempted by the Actor for the specific media.

###2.6.2 Language

Code representing the language in which the experience being recorded in this Statement (mainly) occurred in, if applicable and known. 

Language is used to provide the spoken language for the audio.

The value must be RFC 5646, e.g en, en-US, etc

###2.6.2 Context Extensions

####2.6.2.1 Session ID

<table>
<tr><th align="left">Extension</th><td>session-id
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/session-id</td></tr>
<tr><th align="left">Description</th><td>Used to tell which session the statement is part of. A session starts with the initiated statement and ends with terminated or abandoned statement.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>The LRP SHOULD assign a session id to all the statements sent during a session.</li>
<li>Value of session id MUST be the UUID statement id of the initiated statement, i.e. the initialized statement. </li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td></td></tr>
</table>


###2.6.2.2 CC/Subtitle Enabled

<table>
<tr><th align="left">Extension</th><td>cc-subtitle-enabled
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/cc-subtitle-enabled</td></tr>
<tr><th align="left">Description</th><td>Used to expresses whether subtitle or closed captioning is enabled.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value MUST be boolean i.e. true or false.	</li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td></td></tr>
</table>


###2.6.2.3 CC/Subtitle Language
<table>
<tr><th align="left">Extension</th><td>cc-subtitle-lang
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/cc-subtitle-lang</td></tr>
<tr><th align="left">Description</th><td>Used to express the language of subtitle or closed captioning.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Used only when cc-subtitle-enabled is true.</li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td>The lexical and value spaces of xsd:language are the set of language codes defined by RFC 1766. Examples: "en" for English or "en-US" for American English
</td></tr>
</table>

###2.6.2.4 Frame Rate

<table>
<tr><th align="left">Extension</th><td>frame-rate
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/frame-rate</td></tr>
<tr><th align="left">Description</th><td>Used to express the frame rate or frames per second of a video (or average rate of frames per second in the case of variable frame-rate).</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
</td></tr>
<tr><th align="left">Usage</th><td>Represented as a decimal, such as 29.970.</td></tr>
</table>

###2.6.2.5 Full Screen

<table>
<tr><th align="left">Extension</th><td>full-screen
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/full-screen</td></tr>
<tr><th align="left">Description</th><td>Used to expresses that the video is played in full screen mode.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value MUST be boolean i.e. true or false.	</li>
</ul>

</td></tr>
<tr><th align="left">Usage</th><td></td></tr>
</table>
 

###2.6.2.6 Quality

<table>
<tr><th align="left">Extension</th><td>quality
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/quality</td></tr>
<tr><th align="left">Description</th><td>Used to express the video resolution or quality.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value is a string. e.g. 360, 480, 720, 1080, 2160, sd, hd, 4k, 8k etc.</li>
</ul>
</td></tr>
<tr><th align="left">Usage</th><td></td></tr>
</table>

###2.6.2.7 Screen Size	

<table>
<tr><th align="left">Extension</th><td>screen-size
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/screen-size</td></tr>
<tr><th align="left">Description</th><td>Used to express the device playback screen size or the maximum available screen size for Video playback.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value MUST be in WxH format in pixels. e.g. 1080x960, 640x480, 800x600). i.e. e.g., 360, 480, 720, 1080, etc.</li>
</ul>
</td></tr>
<tr><th align="left">Usage</th><td></td></tr>
</table>

###2.6.2.8 Video Playback Size

<table>
<tr><th align="left">Extension</th><td>video-playback-size
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/video-playback-size</td></tr>
<tr><th align="left">Description</th><td>Used to identify the size in Width x Height of the video as viewed by the user.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value MUST be in WxH format in pixels. e.g. 1080x960, 640x480, 800x600). i.e. e.g., 360, 480, 720, 1080, etc.</li>
</ul>
</td></tr>
<tr><th align="left">Usage</th><td></td></tr>
</table>

###2.6.2.9 Speed

<table>
<tr><th align="left">Extension</th><td>speed
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/speed</td></tr>
<tr><th align="left">Description</th><td>Used to express the play-back speed.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value MUST be represented with decimal or integer values along with an 'x' meaning multiplying factor to the normal speed. e.g. -2x, -1x, -0.5x, 0.5x, 1x, 2x.</li>
</ul>
</td></tr>
<tr><th align="left">Usage</th><td>
<ul>
<li>Negative value means rewind. e.g. -1x, -2x</li>
<li>Positive value with value greater than 1x means fast forward. e.g. 1.5x, 2x, 4x</li>
<li>Positive value with value less than 1x means slow motion play back. e.g. 0.5x, 0.25x, 0.125x</li>
</ul>
</td></tr>
</table>


###2.6.2.10 Track

<table>
<tr><th align="left">Extension</th><td>track
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/track</td></tr>
<tr><th align="left">Description</th><td>Used to identify the name of the audio track in a media object.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value MUST be a string.</li>
</ul>
</td></tr>
<tr><th align="left">Usage</th><td></td></tr>
</table>

###2.6.2.11 User Agent

<table>
<tr><th align="left">Extension</th><td>user-agent
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/user-agent</td></tr>
<tr><th align="left">Description</th><td>Used to identify the User Agent string of the browser, if the video is launched in browser.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value MUST be a string.</li>
</ul>
</td></tr>
<tr><th align="left">Usage</th><td></td></tr>
</table>

###2.6.2.12 Volume

<table>
<tr><th align="left">Extension</th><td>volume
</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/extensions/volume</td></tr>
<tr><th align="left">Description</th><td>Used to identify the loudness of sound specified for a media object.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>Optional.
<ul>
<li>Value MUST be a float value between 0 and 1. </li>
</ul>
</td></tr>
<tr><th align="left">Usage</th><td>Minimum 0 = Mute. Maximum 1 = 100% Volume</td></tr>
</table>

