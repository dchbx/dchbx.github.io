---
layout: default
title: Developer Documentation
---

The ACapi developer documentation describes design concepts, implemented resources and how they are used.  Clients and external systems requiring access to the HBX Resources should ensure they understand the Information Model, the Canonical Vocabulary, the API (Resource, Operation Model, and Event Model) and satisfy the Governance and Rules and Security requirements.

## Components
The following ACApi components are documented:

|Component	|Description |
| --------- | ---------- |
| [Architecture](/architecture)	| A logical representation of DCHBX components and their relationships. |
| [Information Model](/information_model)	| A relational representation of DCHBX data types – the Resources.  |
| [Canonical Vocabulary](/canonical_vocabulary) | A complete XSD vocabulary and data contract for ACapi and OpenHBX Resource Operations and Events. |
| [ACapi](/api)	| Resources, Operations and Events as a Web API and other published endpoint flavors. |

| [Common Services](/common_services)	| Common services supporting the ACapi. |
| [Governance and Rules](/governance)	| Requirements, constraints, and policies to use the ACapi and Common Services. |
| [Message Transport](/message_transport)	| DCHBX ACapi Message Oriented Middleware (MOM) layer. |
| [Security](/security)	| TBD |

ACApi Service Resources include: Broker, Carrier, Employer, Household, Individual, Policy, etc.  Each Resource has associated requests, responses and events (notifications).  A client may make requests to operate or perform processing tasks against Resources or query for information on Resources.  A client may also publish and/or subscribe to events which are fired when Resource actions are initiated, check-pointed, or completed.  The Event Model provides an integration mechanism for all systems which require knowledge of specific event occurrences to synchronize, perform work, or notify downstream.  The Event Model is paramount to maintaining an Authority System and aware systems in general within the HBX.
			
## Release History

|Date	|Version	|Author(s)	|Comments |
| ----- | ----- | ----- | ----- |
| TBD	| 1	    | DCHBX / ACapi	| Initial Release |

