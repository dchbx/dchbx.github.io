# ACapi Developer Documentation

## Purpose
The ACapi documentation describes several core concepts and how to use them.  Clients and external systems requiring access to the HBX Resources should ensure they understand the Information Model, the Canonical Vocabulary, the API (Resource, Operation Model, and Event Model) and satisfy the Governance and Rules and Security requirements.

## Release History

|Date	|Version	|Author(s)	|Comments |
| ----- | ----- | ----- | ----- |
| TBD	| 1	    | DCHBX / ACapi	| Initial Release |

## Components
The following ACapi components are documented <TBD>:

|Component	|Description |
| --------- | ---------- |
| Architecture	| A logical representation of DCHBX components and their relationships. |
| Information Model	| A relational representation of DCHBX data types – the Resources.  |
| Canonical Vocabulary | A complete XSD vocabulary and data contract for ACapi and OpenHBX Resource Operations and Events. |
| ACapi	| Resources, Operations and Events as a Web API and other published endpoint flavors. |
| Common Services	| Common services supporting the ACapi. |
| Governance and Rules	| Requirements, constraints, and policies to use the ACapi and Common Services. |
| Transport	| DCHBX ACapi Message Oriented Middleware (MOM) layer. |
| Security	| TBD |

Examples of DCHBX / OpenHBX Information Model Resources which can be accessed with the ACapi are Broker, Carrier, Employer, Household, Individual, Policy, etc.  Each Resource has operations (requests and queries) and events (notifications) associated with it.  A client may make requests to operate or perform processing tasks against Resources or query for information on Resources.  A client may also publish and/or subscribe to events which are fired when Resource actions are initiated, check-pointed, or completed.  The Event Model provides an integration mechanism for all systems which require knowledge of specific event occurrences to synchronize, perform work, or notify downstream.  The Event Model is paramount to maintaining an Authority System and aware systems in general within the HBX.

			
