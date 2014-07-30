---
layout: default
title: Canonical Vocabulary
---
The ACapi utilizes a Canonical Vocabulary (CV).  The CV defines the schema, message content, and structure for the Health Benefit Exchange.  The various CV schemas and data elements describe the Resources and contain the data contract to fulfill Resource Requests and Events.

External systems, clients, and user systems are expected to use the CV when communicating or transacting with the HBX using the ACapi.  One of the [Common Services](/docs/common_services) is a Transform Service which allows a client to create CV from their formats in order to maintain the HBX data contract for services.

## XML Schemas
CV schemas and descriptions are provided below.  The [Canonical Vocabulary](http://github.com/dchbx/cv) is accessible in a separate project.

| CV XSD	| Description and Use | 
| ----- | --------- | 
| common	| Common or base types, both simple and complex, referenced throughout the ACApi for dependent Resource XSD.| 
| config	| Configuration schema for ACApi site and various protocol implementations of the ACApi service endpoints. | 
| dms       | Document Management System definitions and types. |
| document_storage | Document storage requests and retrieval definitions and types. |
| edi	    | EDI interface schema. | 
| employer	| Employer and Employee Resource definitions, types, requests, and events. | 
| individual	| Individual, ApplicationGroup, and Household Resource definitions, types, requests, and events. | 
| organization	| Broker, Carrier, and HBX Resource definitions and types. | 
| plan	| Qualifying Health Plan (QHP) Resource definitions and types. | 
| policy	| Policy Resource definitions, types, requests, and events. | 
| premium_payment	| Premium Payment Resource definitions and types. | 
| premium_statement	| Premium Statement Resource definitions and types. | 
| process	| Business Process Resource supporting HBX operations definitions and types. | 
| vocabulary | A schema which includes all dependent schema if a single reference schema is desired. | 

## Release History

| Date	| Version	| Author(s)	| Comments | 
| ----- | --------- | --------- | -------- |
| TBD	| 1.0	    | DCHBX / ACapi	 | Initial CV Package Release |
