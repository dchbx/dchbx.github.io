---
layout: default
title: API
---
The ACApi offers a flexible framework upon which to build health insurance marketplace technology. The design encourages reuse and extension by applying modern, proven system development principles:

* Convention over configuration
* Open source tools and systems
* Test-first development
* RESTful Web services

Covers individual and SHOP marketplaces.



Clients access to the Resource Operation Model and the Resource Event Model.  Resources are the HBX Information Model entities grouped logically to handle operations (requests and responses) and events (notifications).  Some examples of the Resources in the HBX are Individual, Employer, Policy, and Carrier, just to name a few.

The API is structured in a RESTful manner yielding a very logical mechanism for creating, reading, updating, and deleting (CRUD operations) information within the OpenHBX.  The API will be exposed through different connectors or endpoints.  The HTTP endpoints we believe will be the most commonly accessed endpoints and the majority of the initial documentation will place focus there.  Other endpoints or connectors offered include JMS and where appropriate, direct AMQP.

The API s implemented on top of a set of Common Services which utilize an XML-based Canonical Vocabulary.  The Common Services are essential, building block services which are required to fulfill and complete OpenHBX Resource operations and standard services.  The Canonical Vocabulary is an XSD which encapsulates the necessary data elements for Resource events and operations.

Provisioning a complete Resource Operation Model and a Resource Event Model allows the OpenHBX to effectively become the Authority System for:

- HBX Level Identifiers (Members / Individuals and other Resources)
- Carrier Transactions (Process and Resource Operation Level State Machine)

This yields a System of Record or Authority System capable of and responsible for maintaining enterprise-level data integrity in the HBX – between external systems and for the HBX users.

## Versions

| Component	|Version	| Date	|Comments |
| ----- | ----- | ----- | ----- |
| API	| 1	    | 6/18/2014	| Initial Release - Evolving |

## General Guidelines
This document provides guidelines and examples of how the API is designed.  OpenHBX has attempted to leverage many concepts to encourage consistency, maintainability, and best practices across applications that will utilize the API and within the API itself.  The OpenHBX API aims to balance a truly RESTful API interface with a positive developer and user experience.

The concepts illustrated here borrow heavily from:
- Web API Design, by Brian Mulloy of Apigee
- API Façade Pattern, by Brian Mulloy of Apigee

## Concepts and Conventions
This section details the concepts and conventions employed in the OpenHBX API design.  The OpenHBX team believes this offers a highly intuitive and consistent approach.

## Message Transport Interface ##

### Requests ###

### Responses ###

### Events ###

## HTTP Interface ##

### Requests/Responses ###

### Events ###

### URLs

URLs to gain access to the Web API for Resources generally follow this convention:

	<hbx_reference_id>/openhbx/<resource>/<version>/<resource_type>, or
	<hbx_reference_id>/openhbx/<resource>/<version>/<resource_type/<id>

where,

- hbx_reference_id = the Federal assigned identifier for the exchange.  The DC Health Benefits Exchange Federal ID is “DC0”.
- resource = the identifies the API call as a Resource Operation
- version = the version number of the API, such as “v1” or “v2”
- resource_type = the specific HBX Resource type which is the subject of the API call
- id = a specific identifier of a specific type of Resource

The URLs are designed to reference Resources as nouns and use the HTTP verbs to operate on the Resources.  The following table illustrates this concept by showing a cross-reference between the Resource in the URL and the HTTP verb used in the request:

| Resource	| POST (Create)	| GET (Read) | PUT (Update) | DELETE (Delete) |
| --------- | ------------- | ---------- | ------------ | --------------- |
| /employers |	N/A |	List employers	| Update or modify employers |	Delete employers |
| /employers#by_id	| N/A	 | Return an employer instance identified by the specified identifier | Update a specific employer identified by the id, if the employer exists, otherwise, error | Delete the specific employer identified by the id, if the employer exists |
| /employers/id/employees | Create or add a new employee to the roster of a specific employer | List the employees on the roster of a specific employer | Update or modify employees of a specific employer | Delete employees for a specific employer |
| /employers/id/employees/id | N/A | List a specific employee on the roster of a specific employer | Update or modify a specific employee of a specific employer	| Delete a specific employee of a specific employer |

Developers and users of the ACapi should be able to logically extend this intuitive design and based on the Resources involved, can determine the URL to access the Resource and operation they need to invoke.  The URLs and all aspects will be further defined within specific Resource referenced in the API documentation.  Some basic tenets are as follows:

* URLs should generally be limited to referencing just two layers of Resources, e.g. “/employers/<id>/employees”.  Once an employee or list of employees for a specific employer is obtained, further references can be made to specific employees, if required.
* One should never have to go below a specific resource more than two layers in any single request or response.
* Verbs will not generally appear in any base URL
* The HTTP verbs in the protocol will serve to imply the operations on the Resources

### Parameters ###

The basic design above is meant to greatly simplify the API for the developer and user experience.  Obviously, this approach isn’t complete and there will be a greater complexity required for accessing or operating on most Resources.  Complexity is built in using the HTTP parameters.  For example, accessing a list of active employees for a specific employer, or a list of terminated employees for a specific employer, or specific employees terminated since a specific date might be handled as follows:

	DC0/openhbx/resource/v1/employers/1234/employees?status=active, or
	DC0/openhbx/resource/v1/employers/1234/employees?status=terminated, or
	DC0/openhbx/resource/v1/employers/1234/employees?status=terminated&effective=2014-01-01

Versioning is handled within the URL and redirection within the HBX Enterprise can be managed internally.  Offering versioning in the URL directly allows all clients and users to migrate to versions of the OpenHBX API at their own pace.  The project can certainly dictate sunset terms on specific versions as the API matures and progresses, but the idea is not to leave anyone behind.

### Error Handling
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

## Resources
A list of the ACapi HBX Resources can be found here.  The Resource page describes all resources which are exposed in the API.  Also described are the Resource Operations Model and Resource Event Model.

