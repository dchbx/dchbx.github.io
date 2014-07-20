---
layout: default
title: Canonical Vocabulary
---
The ACapi utilizes a Canonical Vocabulary (CV).  The CV defines the schema, message content, and structure for the Health Benefit Exchange.  The various CV schemas and data elements describe the Resources and contain the data contract to fulfill Resource Operations and Events.

External systems, clients, and user systems are expected to use the CV when communicating or transacting with the HBX using the ACapi.

## Release History

| Date	| Version	| Author(s)	| Comments | 
| ----- | --------- | --------- | -------- |
| TBD	| 1.0	    | DCHBX / ACapi	 | Initial CV Package Release |

## XSD
CV schemas and descriptions

| XSD	| Description	| 
| ----- | --------- | 
| common	| Common or base types referenced throughout the schemas. | 
| config	| Configuration schema. | 
| edi	    | EDI interface schema. | 
| employer	| SHOP employer schema. | 
| individual	| Individual resource schema. | 
| organization	| Organization schema.  Can represent Brokers, Carriers, Employers, HBX, etc. with organizational information. | 
| plan	| Qualifying Health Plan (QHP) schema. | 
| policy	| Policy schema.  A policy generally represents a group of people covered under a specific QHP for a specific period of time. | 
| premium_payment	| Premium payment schema. | 
| premium_statement	| Premium statement schema. | 
| process	| Process and Operation schema.  The process schema will be expanded to manage operations within the OpenHBX. | 
| vocabulary	| CV information schema. | 




