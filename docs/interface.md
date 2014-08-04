---
layout: default
title: Interface
---

The ACApi offers a flexible Interface Model upon which to build and connect health insurance marketplace technology components.  It is designed to offer the clients and client systems a high-level access to the functions required while abstracting them completely from the operations and underlying processing.  

ACApi, in some respects, can be analagous to the backplane technology that revolutionized the personal computer industry in the late 1970s and beyond.  A backplane is essentially a computer bus.  They were crafted on circuit boards and allowed a parallel connection to be made along the board through the various connectors.  The backplane allowed disparate "pluggable" components which could fit into the connectors to become usable by the computer.  Computers generally plugged in expansion cards or expansion hardware that worked with the backplane or the bus.  In the HBX domain, components which fulfill HBX functions and roles can be plugged in and connected by the ACApi.

![ACApi Interface Model](/assets/acapi_interfaces.png)

In the same way that a backplane could plug in different hardware from multiple vendors, the ACApi is designed with the functional set and interfaces to work with components fulfilling the HBX Functions and Roles.  It yields a flexible, plug-and-play approach to integrating the technology.  It will enrich and extend existing implementations and work with new implementations.

### Multiple Protocols ###

ACApi is exposed in several protocols and endpoint connector options.  ACApi is generally structured in the RESTful manner resulting in a very logical mechanism for retrieving information and operating on Resources in the HBX.

| Protocol | Description |
| -------- | ----------- |
| HTTP	| Web API and web services |
| JMS	| Pub/Sub and Point-to-Point services | 
| AMQP	| Transport layer access for AMQP capable clients and client systems | 

The ACApi HBX Resource Requests and Events Model are accessible through all of these protocols.  Some of the protocols possess advantages over others.  There are always trade-offs.  The relative advantages and disadvantages are highlighted:

| Protocol | Pros | Cons |
| -------- | ---- | ---- |
| HTTP	| Common, legacy | Synchronous, transaction control, error handling, and recovery, polling model |
| JMS	| Pub/Sub and Point-to-Point, asynchronous, persistence, durability | Less common integration, Potential higher level of integration or development work required | 
| AMQP	| Lower-level, direct ACApi transport access | Even less common integration, Potential higher level of integration or development work required |

Client integration of the messaging protocol(s), JMS or AMQP, is generally preferred over the HTTP protocol for several reasons.  Some of the larger advantages in a messaging interface include:

* Asynchronous vs Synchronous (Requests/Responses)
* Publishing vs Polling (Events)
* Error Handling, Recovery, and Logging (Transaction Management)
* Persistance and Durability (Failure Mitigation)

The HTTP protocol integration is likely more common among legacy systems as an existing protocol.  It is provided for easy on-ramp integration reducing the level of effort.

#### HTTP Interface ####

##### Serialization #####
* XML 
* SOAP
* JSON

##### Requests/Responses #####

##### Events #####
Polling

#### Message Transport Interfaces ####

##### Serialization #####
* XML
* SOAP

##### Requests #####

##### Responses #####

##### Events #####
Pub/Sub


### Error Handling ###
Error handling uses HTTP status codes for all protocols.

The ACApi will utilize a small subset of the standard HTTP status codes – enough to provide the clients and users with adequate information.

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
