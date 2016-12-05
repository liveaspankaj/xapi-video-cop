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
<tr><th align="left" nowrap>LRP Obligations</th><td>The LRP MUST use "Initialized" in the first statement in the video session.  The LRP MUST NOT issue multiple statements with "Initialized" for the same video session.</td></tr>
<tr><th align="left">Usage</th><td>Used when the actor generally played a video or clicked the play button. Also used when the video starts after an actor seeked to a new position in video.</td></tr>
</table>

<a name="verbs_paused"></a>
###2.3.2 Paused
<table>
<tr><th align="left">Verb</th><td>Paused</td></tr>
<tr><th align="left">ID</th><td>https://w3id.org/xapi/video/verbs/paused</td></tr>
<tr><th align="left">Description</th><td>Indicates that the actor started experiencing the recorded media object.</td></tr>
<tr><th align="left" nowrap>LRP Obligations</th><td>The LRP MUST use "Initialized" in the first statement in the video session.  The LRP MUST NOT issue multiple statements with "Initialized" for the same video session.</td></tr>
<tr><th align="left">Usage</th><td>Used when the actor generally played a video or clicked the play button. Also used when the video starts after an actor seeked to a new position in video.</td></tr>
</table>

##Extensions

###Session ID

The LRP can assign a Session ID to all the statements sent during a session. 

The value of the Session ID must match the statement id of the first statement of the session, i.e. the initialized statement. 

A session starts with the initialized statement when a learner starts a video.

The session ends with a terminated or abandoned verb. 

Session ID is Optional.


