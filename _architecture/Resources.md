# Resources
The OpenHBX API exposes the following Resources to the client.  Each Resource has an associated set of Operations and Events.  Refer to the Resource specific page for details on Operations and Events associated with a given Resource.1

| Resource	| Description |
| --------- | ----------- |
| Broker	| Qualifying Health Plan sellers representing Carrier provided plans.  Brokers package, bundle, and sell health and dental plans. | 
| Carrier	| Carriers provide the Qualifying Health Plans offered. | 
| Employer	| Employers are groups that contain employees.  Employers offer open enrollment periods for employees to be able to select Qualifying Health Plans through their employer. | 
| Application Group	|  Application Group ties together the entities in an enrollment process – Employers, Households, Individuals, Policies, etc. | 
| Household	|  Households are groups that contain Individuals.  Generally there is a primary Individual and Individuals associated in various relationships to the primary Individual. | 
| Individual	| An Individual is the discrete unit of insured within the HBX. | 
| Policy	| Policy is a grouping that binds a set of Resources together under a session or key within the HBX. | 

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
