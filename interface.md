---
layout: default
title: Interface
---

Defining abstraction layer / hardware backplane.  Not one protocol, not one vendor. Flexible plug and play approach.  Will work with new implementation, or extend existing.

Clients access to the Resource Operation Model and the Resource Event Model.  Resources are the HBX Information Model entities grouped logically to handle operations (requests and responses) and events (notifications).  Some examples of the Resources in the HBX are Individual, Employer, Policy, and Carrier, just to name a few.

![ACApi Interface Model](/assets/acapi_interfaces.png)


## Multiple Protocols ##
The ACApi is structured in a RESTful manner yielding a very logical mechanism for creating, reading, updating, and deleting (CRUD operations) information within the OpenHBX.  The ACApi will be exposed through different connectors or endpoints.  

The ACApi s implemented on top of a set of resources (Web services or messaging endpoints) which utilize an XML-based [Canonical Vocabulary](/canaonical_vocabulary). The Canonical Vocabulary is an XSD which encapsulates the necessary data elements for Resource events and operations.

Protocol Interfaces:

# Messaging: AMPQ, JSMS
# HTTP (SOAP)

Meessagin is preferred.  Explain pros & cons/differences

* Sync vs Async
* Push vs. polling (e.g. eventing model)
* Error handling, revoery and logging
* Persistance/durability between network and service failures
* Integration level of effort: legacy systems, existing protocols


## Message Transport Interface ##

### Serialization ###
* XML 
* SOAP

### Requests ###

### Responses ###

### Events ###
Pub/sub

## HTTP Interface ##


### Serialization ###
* XML 
* SOAP
* JSON

### Requests/Responses ###

### Events ###
Polling...


Provisioning a complete Resource Operation Model and a Resource Event Model allows the OpenHBX to effectively become the Authority System for:

- HBX Level Identifiers (Members / Individuals and other Resources)
- Carrier Transactions (Process and Resource Operation Level State Machine)

This yields a System of Record or Authority System capable of and responsible for maintaining enterprise-level data integrity in the HBX – between external systems and for the HBX users.

## General Guidelines
This document provides guidelines and examples of how the ACApi is designed.  OpenHBX has attempted to leverage many concepts to encourage consistency, maintainability, and best practices across applications that will utilize the ACApi and within the ACApi itself.  The OpenHBX ACApi aims to balance a truly RESTful ACApi interface with a positive developer and user experience.

The concepts illustrated here borrow heavily from:
- Web ACApi Design, by Brian Mulloy of Apigee
- ACApi Façade Pattern, by Brian Mulloy of Apigee

## Concepts and Conventions
This section details the concepts and conventions employed in the OpenHBX ACApi design.  The OpenHBX team believes this offers a highly intuitive and consistent approach.

## Integration Layer
The ACapi, Resource Operations Model and Resource Events Model is realized in an Integration Layer built on the following components:

| Component	| Description |
| --------- | ----------- |
| Connectors / Endpoints  | Interfaces and on-ramps to the Operation and Event Models | 
| Canonical Vocabulary	| Lingua Franca of the Integration Layer, the Operation Model, and Event Model | 
| Common Services	| Integration Layer base services | 
| Governance	| Integration Layer governance and rules | 
| MQ / Messaging Exchange	| Integration Layer MOM – Transport and Delivery. | 
| Event Model	| Pub/Sub Model for the Integration Layer and for External Systems | 
| Operation Model	| PTP Model for the Integration Layer and for External Systems | 

EMBED:  IMAGE OR DIAGRAM AND EXPLANATION OF COMPONENTS AND USE
 
## Event Model
The Event Model design provides event subscription and event publication.  The Integration Layer exposes the interfaces and endpoints allowing it to subscribe to events published by external systems.  The Integration Layer also establishes the interfaces and endpoints allowing it to publish or re-publish events which external systems can subscribe to or consume.  By design, the events are intended to be lightweight messages with essential or critical data elements such as the pertinent identifiers and URIs to the Resources associated with the event.

The Event Model is exposed through various endpoints and protocols, making it accessible to clients. The three, major endpoint types and protocol connectors offered to clients, both external and internal are:

| Endpoint / Connector	| Description |
| --------------------  | ----------- |
| HTTP	| HTTP/SOAP/WSDL endpoint |
| JMS	| JMS endpoint – pub/sub model | 
| AMQP	| AMQP endpoint – a direct endpoint to the MQ layer for AMQP capable clients | 

The request elements in an event are specific to the Resources involved.  Depending on the protocol a client utilizes to publish the event, request elements may be supplied different, e.g. as HTTP parameters name/value pairs or as JMS message properties.  The subscribers to events will be able to use the request elements to synchronize information in the HBX, perform necessary operational tasks related to receiving events, or use them to republish enriched events for additional subscribers to the Event Model.

EMBED: DIAGRAM ?? – Architecture / Component diagram displaying the various Protocol Endpoints exposed for pub and sub Eventing – need accuracy

## Operation Model
The Operation Model design provides HBX Resource operations and Resource access in a RESTful design.  The Integration Layer exposes the interfaces and endpoints allowing clients, external and internal, to use the operations to perform necessary functions on various Resources.

The Operation Model is exposed through various endpoints and protocols, making it accessible to clients. The three, major endpoint types and protocol connectors offered to clients, both external and internal are:

| Endpoint / Connector	| Description |
| --------------------  | ----------- |
| HTTP	| HTTP/SOAP/WSDL endpoint |
| JMS	| JMS endpoint – pub/sub model | 
| AMQP	| AMQP endpoint – a direct endpoint to the MQ layer for AMQP capable clients | 

EMBED:  DIAGRAM ?? – Architecture / Component diagram displaying the various Protocol Endpoints exposed for Operations – similar to Event Model but needs specific for Common Services – need accuracy

### URLs

URLs to gain access to the Web ACApi for Resources generally follow this convention:

	<hbx_reference_id>/openhbx/<resource>/<version>/<resource_type>, or
	<hbx_reference_id>/openhbx/<resource>/<version>/<resource_type/<id>

where,

- hbx_reference_id = the Federal assigned identifier for the exchange.  The DC Health Benefits Exchange Federal ID is “DC0”.
- resource = the identifies the ACApi call as a Resource Operation
- version = the version number of the ACApi, such as “v1” or “v2”
- resource_type = the specific HBX Resource type which is the subject of the ACApi call
- id = a specific identifier of a specific type of Resource

The URLs are designed to reference Resources as nouns and use the HTTP verbs to operate on the Resources.  The following table illustrates this concept by showing a cross-reference between the Resource in the URL and the HTTP verb used in the request:

| Resource	| POST (Create)	| GET (Read) | PUT (Update) | DELETE (Delete) |
| --------- | ------------- | ---------- | ------------ | --------------- |
| /employers |	N/A |	List employers	| Update or modify employers |	Delete employers |
| /employers#by_id	| N/A	 | Return an employer instance identified by the specified identifier | Update a specific employer identified by the id, if the employer exists, otherwise, error | Delete the specific employer identified by the id, if the employer exists |
| /employers/id/employees | Create or add a new employee to the roster of a specific employer | List the employees on the roster of a specific employer | Update or modify employees of a specific employer | Delete employees for a specific employer |
| /employers/id/employees/id | N/A | List a specific employee on the roster of a specific employer | Update or modify a specific employee of a specific employer	| Delete a specific employee of a specific employer |

Developers and users of the ACapi should be able to logically extend this intuitive design and based on the Resources involved, can determine the URL to access the Resource and operation they need to invoke.  The URLs and all aspects will be further defined within specific Resource referenced in the ACApi documentation.  Some basic tenets are as follows:

* URLs should generally be limited to referencing just two layers of Resources, e.g. “/employers/<id>/employees”.  Once an employee or list of employees for a specific employer is obtained, further references can be made to specific employees, if required.
* One should never have to go below a specific resource more than two layers in any single request or response.
* Verbs will not generally appear in any base URL
* The HTTP verbs in the protocol will serve to imply the operations on the Resources

### Parameters ###

Requests, responses, events:
Global: openhbx
Local: dc0 (exchange_id)

The basic design above is meant to greatly simplify the ACApi for the developer and user experience.  Obviously, this approach isn’t complete and there will be a greater complexity required for accessing or operating on most Resources.  Complexity is built in using the HTTP parameters.  For example, accessing a list of active employees for a specific employer, or a list of terminated employees for a specific employer, or specific employees terminated since a specific date might be handled as follows:

```ruby
urn:openhbx:requests:v1:employers#create 
```

	urn:openhbx/resource/v1/employers/1234/employees?status=active, or
	urn:openhbx/resource/v1/employers/1234/employees?status=terminated, or
	urn:openhbx/resource/v1/employers/1234/employees?status=terminated&effective=2014-01-01

Versioning is handled within the URL and redirection within the HBX Enterprise can be managed internally.  Offering versioning in the URL directly allows all clients and users to migrate to versions of the OpenHBX ACApi at their own pace.  The project can certainly dictate sunset terms on specific versions as the ACApi matures and progresses, but the idea is not to leave anyone behind.

## Error Handling
Error handling uses HTTP status calls for all protocols.

The OpenHBX will utilize a small subset of the basic HTTP status codes – enough to provide the clients and users with adequate information:

| HTTP Status Code	| Description / Interpretation |
| ----------------  | ---------------------------- |
| 200	| OK – General success status response code |
| 201	| CREATED – Request fulfilled and resulted in a new resource being created |
| 304	| NOT MODIFIED – Client or User has latest, no need to retransmit a copy |
| 400	| BAD REQUEST – Request cannot be fulfilled, usually bad syntax |
| 401	| UNAUTHORIZED – Authentication failed |
| 403	| FORBIDDEN – Not authorized |
| 404	| NOT FOUND – Reference by the URL was not found (currently) |
| 500	| INTERNAL SERVER ERROR – General error on the server side |

