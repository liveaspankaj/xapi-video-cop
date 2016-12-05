# xAPI Statement Data Model


##Statement ID

The LRP MUST assign a statement id property in UUID format (as defined in the xAPI specification) for all statements it issues.


##Actor

The Actor property must be defined as per the xAPI Specification. 

When the video is launched in an LMS, Actor must be provided by the LMS. 

#Verbs





##Extensions

###Session ID

The LRP can assign a Session ID to all the statements sent during a session. 

The value of the Session ID must match the statement id of the first statement of the session, i.e. the initialized statement. 

A session starts with the initialized statement when a learner starts a video.

The session ends with a terminated or abandoned verb. 

Session ID is Optional.


