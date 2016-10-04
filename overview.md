# 1.0 Overview



# 1.1 Definitions
* [Activity](#def-activity)
* [Activity Provider (AP)](#def-activity-provider)
* [Actor](#def-actor)
* [Application Programming Interface (API)](#def-api)
* [Authentication](#def-authentication)
* [Authorization](#def-authorization)
* [Community of Practice](#def-community-of-practice)
* [Document Profile Resource](#def-document-profile)
* [Endpoint](#def-endpoint)
* [Experience API (xAPI)](#def-experience-api)
* [Immutable](#def-immutable)
* [Internationalized Resource Identifier (IRI)](#def-iri)
* [Internationalized Resource Locator (IRL)](#def-irl)
* [Inverse Functional Identifier](#def-inverse-functional-identifier)
* [Learning Experience](#def-learning-experience)
* [Learning Management System (LMS)](#def-learning-management-system)
* [Learning Record](#def-learning-record)
* [Learning Record Consumer (LRC)](#def-learning-record-consumer)
* [Learning Record Provider (LRP)](#def-learning-record-provider)
* [Learning Record Store (LRS)](#def-learning-record-store)
* [Metadata Consumer](#def-metadata-consumer)
* [Metadata Provider](#def-metadata-provider)
* [Persona](#def-persona)
* [Profile](#def-profile)
* [Registration](#def-registration)
* [Representational State Transfer (REST)](#def-rest)
* [Service](#def-service)
* [Statement](#def-statement)
* [Tin Can API (TCAPI)](#def-tcapi)
* [Verb](#def-verb)
* [Vocabulary](#def-vocabulary)

<a name="def-activity" ></a>

__Activity__: A type of Object making up the "this" in "I did this"; it is something 
with which an Actor interacted. It can be a unit of instruction, experience, or performance that is 
to be tracked in meaningful combination with a Verb. Interpretation of Activity is broad, meaning that 
Activities can even be tangible objects such as a chair (real or virtual). In the Statement "Anna 
tried a cake recipe", the recipe constitutes the Activity in terms of the xAPI Statement. Other 
examples of Activities include a book, an e-learning course, a hike, or a meeting.

<a name="def-activity-provider" ></a>

__Activity Provider (AP)__: Now referred to as a Learning Record Provider. This change differentiates that 
the activity itself is not always the responsibility of software, rather just the tracking portion is. 

<a name="def-actor" ></a>

__Actor__: An individual or group representation tracked using Statements performing an action within 
an Activity.  Is the "I" in "I did this".

<a name="def-api" ></a>

__Application Programming Interface (API)__: A set of rules and standards created to allow access into 
a software application or tool.  

<a name="def-authentication" ></a>

__Authentication__: The concept of verifying identity. Authentication allows interactions between two 
"trusted" parties.

<a name="def-authorization" ></a>

__Authorization__: The affordance of permissions based on role; the process of making one party 
"trusted" by another.

<a name="def-client" ></a>

__Client__: Refers to any entity that might interact through requests. Some examples could be a 
Learning Record Provider, a Learning Record Consumer, a Learning Record Store (LRS), or a Learning 
Management System (LMS).

<a name="def-community-of-practice" ></a>

__Community of Practice (CoP)__: A group of practitioners connected by a common cause, role or purpose, which operates in a common 
modality. CoPs are focused on implementing xAPI within a specific knowledge domain or use case. CoPs or independent developers, 
can create domain-specific vocabularies, profiles, and recipes. These practices usually involve work around defining use cases 
and curating the various vocabulary terms, synonyms, and other related metadata that might be preferred within a CoP. They can 
also reuse existing vocabularies, profiles, and recipes already published by other CoPs or participants of the xAPI community.

<a name="def-document-profile" ></a>

__Document Profile Resource__: A construct where information about the learner or activity is kept, typically in name/document pairs 
that have meaning to an instructional system component. Not to be confused with [Profile](#def-profile).

<a name="def-endpoint" ></a>

__Endpoint__: An entry point in a service-oriented-architecture.  xAPI mirrors this approach with resources 
by defining the IRI from which communication takes place as an endpoint.

<a name="def-experience-api" ></a>

__Experience API (xAPI)__: The collection of rules articulated in this document which determines how learning 
experiences are defined, formatted, and exchanged so that independent software programs can exchange and make 
use of this information.

<a name ="def-immutable" ></a>

__Immutable__:  Adjective used to describe things which cannot be changed. With some exceptions, Statements in the xAPI 
are immutable. This ensures that when Statements are shared between LRSs, multiple copies of the Statement remain the same.

<a name="def-iri" ></a>

__Internationalized Resource Identifier  (IRI)__: A unique identifier which could be an IRL. Used to identify an object 
such as a verb, activity or activity type. Unlike URIs, IRIs can contain some characters outside of the ASCII character 
set in order to support international languages. 

IRIs always include a scheme. This is not a requirement of this standard, but part of the definition of IRIs, per 
[RFC 3987](http://www.ietf.org/rfc/rfc3987.txt). What are sometimes called "relative IRIs" are not IRIs.

<a name="def-irl" ></a>

__Internationalized Resource Locator (IRL)__:  In the context of this document, an IRL is an IRI that when translated 
into a URI (per the IRI to URI rules), is a URL. 

<a name="def-inverse-functional-identifier" ></a>

__Inverse Functional Identifier__: An identifier which is unique to a particular persona or Group.

<a name="def-learning-experience" ></a>

__Learning Experience__: An event associated with learning.  It is highly diverse as far as what it can be.  
Examples include reading a book, taking an online course, going on a field trip, engaging in self-directed 
research, or receiving a certificate for a completed course.

<a name="def-learning-management-system" ></a>

__Learning Management System (LMS)__: "A software package used to administer one or more courses to one or more learners. 
An LMS is typically a web-based system that allows learners to authenticate themselves, register for courses, complete 
courses and take assessments" (Learning Systems Architecture Lab definition). An LMS in this document is used as an 
example of how a user is identified as "trusted" within a system and able to access its Learning Experiences.

<a name="def-learning-record" ></a>

__Learning Record__: An account of a learning experience that is formatted according to the rules of xAPI.  A Learning Record
takes on many forms, including Statements, documents, and their parts.  This definition is intended to be all-inclusive.

<a name="def-learning-record-consumer" ></a>

__Learning Record Consumer (LRC)__: An xAPI Client that accesses data from Learning Record Store(s) with the intent of processing 
the data, including interpretation, analysis, translation, dissemination, and aggregation.

<a name="def-learning-record-provider" ></a>

__Learning Record Provider (LRP)__: An xAPI Client that sends data to Learning Record Store(s).  Often, the Learning Record 
Provider will create Learning Records while monitoring a learner as a part of a Learning Experience.

<a name="def-learning-record-store" ></a>

__Learning Record Store (LRS)__: A server (i.e. system capable of receiving and processing web requests) that is responsible 
for receiving, storing, and providing access to Learning Records.

<a name="def-metadata-consumer" ></a>

__Metadata Consumer__: A person, organization, software program or other thing that seeks to determine the meaning represented
by an IRI used within this specification and/or retrieves metadata about an IRI. An LRS might or might not be a metadata consumer. 

<a name="def-metadata-provider" ></a>

__Metadata Provider__: A person, organization, software program or other thing that coins IRIs to be used within 
this specification and/or hosts metadata about an IRI. 

<a name="def-persona" ></a>

__Persona__: A set of one or more representations which defines an Actor uniquely.  Conceptually, this is like 
having a "home email" and a "work email".  Both are the same person, but have different data, associations, etc.

<a name="def-profile" ></a>

__Profile__: A specific set of rules and documentation for implementing xAPI in a particular context. Profiles generally provide a 
particular vocabulary of terms, some created specifically for the profile, and some are referenced from other vocabularies. 
Sometimes a profile might provide multiple vocabularies for different situations, and sometimes someone might curate a vocabulary 
from multiple sources without creating a profile.  Not to be confused with [Document Profile Resource](#def-document-profile).

<a name="def-registration" ></a>

__Registration__: An instance of an Actor experiencing a particular Activity.

<a name="def-rest" ></a>

__Representational State Transfer (REST)__: An architecture for designing networked web services.
It relies on HTTP methods and uses current web best practices.

<a name="def-service" ></a>

__Service__: A software component responsible for one or more aspects of the distributed learning process. 
An LMS typically combines many services to design a complete learning experience.

<a name="def-statement" ></a>

__Statement__: A data sctructure showing evidence for any sort of experience or event which is to be tracked 
in xAPI as a Learning Record.  A set of several Statements, each representing an event in time, might be used 
to track complete details about a learning experience.  

<a name="def-tcapi"></a>

__Tin Can API (TCAPI)__: The previous name of the API defined in this document, often used in 
informal references to the Experience API.  

<a name="def-verb" ></a>

__Verb__: Is the action being done by the Actor within the Activity within a Statement. 
A Verb represents the "did" in "I did this".
