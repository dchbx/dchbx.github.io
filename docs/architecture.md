---
layout: default
title: Architecture
---

## Reference Architecture

The ACApi architecture is a reference architecture in the Health Benefit Exchange (HBX) domain.  A reference architecture in the field of software architecture or enterprise architecture provides a generalized, template solution for an architecture in a particular domain. It provides a common vocabulary with which to discuss implementations, often with the aim to stress commonality.

HBX functional capabilities are delivered by several referential components.  Implementations of HBX functions may deliver all of these functions or only a subset.  The ACApi is conceived to be a "plug-and-play" means to integrate or potentially fulfill one or all of these functional components.

| HBX Reference Component	| HBX Functions - Description | 
| --------- | ----------- |
| Registration (Individual or SHOP) | Intake - register and become known to the HBX |
| Eligibility (Individual) | Qualification - determine eligibility to qualify for plans and assistance |
| Plan Shopping (Individual or SHOP) | Plan comparison and selection - user evaluation and selection of Qualifying Health Plans (QHP) |
| EDI | Carrier electronic data interchange - transactions with the Carriers |
| Premium Billing | Premium billing and management - manage premium billing for the Individual and SHOP marketplaces |
| Exchange Operations Portal | Exchange management and operations - interface into operations, audit, and authority |
| Notices and Reporting | Communication and intelligence - internal and external |
| API | Resources - Requests and Events, functions | 


The ACApi is designed to be an abstraction layer providing stable mechanisms for these functional components to interact and communicate, even in potential multi-tenant situations.  <Figure 1. below illustrates the District of Columbia HBX (DCAS and DCAS Infrastructure) and Potential Partner (Tenant Systems).  The Tenant Systems components plugged into the OpenHBX representing the functional components, using the ACApi.>

![ACApi Architecture](/assets/hapi_architecture.png)
**Figure 1.  DCHBX (HealthLink) Architecture**

ACApi combines an Application Programmable Interface (API) based in Service-oriented Architecture (SOA) principles.  A major key in the ACApi design is the decoupling of business logic from business process.  The SOA nature of the ACApi design allows more flexibility, extensibility, and scalability.  Flexibility is achieved by creating services behind the ACApi abstraction layer, which is exposed to the clients via several protocols.  The same services are rendered but in ways which clients can consume.  Extensibility is offered because new consumers and clients can leverage or tap into the ACApi services, Resource requests, and  Resource events without disrupting other existing business processes.  Scalability is achieved in the horizontal layers of the architecture for loading and throughput.  The architecture can also be distrubuted geographically across layering for fault tolerance and high-availability.


## DCHBX Architecture

The DCHBX was built using several COTS products and other integrated components to fulfill Reference Architecture HBX functions.

### DCAS Infastructure Components
The following is a list and short description of the DCHBX components:

| DCHBX Component	| Function / Description | 
| --------- | ----------- |
| Curam | Intake, Registrations, Enrollment, and Eligibility |
| Connecture | Plan Shopping and Management (SHOP) |
|	NFP | Financials, Premium Billing |
| DCNet Cloud | Network Infrastructure / Internal Backbone |
| Business Objects and Notices | Business Intelligence, Notices, and Reporting | 
| Identity Management | Single-Sign On |
| ORACLE B2B Gateway | EDI and Carrier Integration |
| ORACLE ESB (Service Bus) | Services and Component Integration |
| REST API | ACApi - Service Requests and Events |
| Glue DB | Exchange Operations / Exchange Operations Portal |
| FDISH | Federal Web Service Gateway:  DHS, DHHS, SSA, IRS |
| DC Local Hub | DC Service Gateway:  DC DMV, DC DHS |



