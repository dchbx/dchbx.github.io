---
layout: default
title: Architecture
---

Introduce architecture and explain difference between general and reference (DCHBX)

ACApi is a Service-oriented Architecture (SOA).... describe what that means.  Flecibility, extensibility, scalability... 

Key concept: decouple business logic from process.

The Architecture is a system level, logical representation of the DCHBX / OpenHBX components and their relationships.  It illustrates groups of functions and systems in a way that depicts their basic HBX interaction and dependencies.


## Architectural

| Component	| Description | 
| --------- | ----------- |
| Registration (Individual or SHOP)
| Eligibility (Individual)
| Plan Shopping (individual or SHOP)
| EDI
| Premium Billing
| Exchange Operations portal
| Notices and Reporting

**DIAGRAM – Andy’s ACapi Architecture Block Diagram Here (based on Maryland diagram**


The following is a list and short description of the components in the OpenHBX Architecture.  The OpenHBX Architecture fulfills the functions of the specific HBX, such as DCHBX, but leaves the areas “Open” versus specific to a COTS product or other component:

* Component	Description
* Individual Eligibility & Plan Shopping	
* SHOP (Business) Eligibility & Plan Shopping	Small Business Health Option Program (SHOP) manages employers, their employees, eligibility, and plan selection.
* Premium Management Providers	Premium Management Providers (PMP) manage plan premiums, billing, and financials.
* Integration Layer	
* Carrier Integration	


Figure 1	DCHBX (Healthlink) Architecture
IMAGE of DCHBX (Healthlink) Architecture embedded here
 
## Reference Architecture

What is DCAS?  Which components?

### DCAS COTS Components
The following is a list and short description of the DCAS COTS components in the HBX:

| Component	| Description | 
| --------- | ----------- |
| Curam | Enrollment and Eligibility |
| Connecture | Plan Shopping and Management (SHOP) |
|	NFP | Financials and Premium Management |
 
### DCAS Infrastrucure Components
The following is a list and short description of the DCAS core components in the HBX:

| Component	| Description | 
| --------- | ----------- |
| DCNet Cloud | Network Infrastructure / Internal Backbone
| Business Objects | Business Intelligence / Reporting / Notices | 
| ORACLE Identity Management | Single-Sign On |
| ORACLE Service Bus | Services and Integration |
| ORACLE B2B Gateway | EDI Support and Integration |
| Local Hub | Additional Transport |


The following is a list and short description of the components in the DCHBX Architecture:

| Component	| DCHBX Component | 
| --------- | --------------- |
| Registration | Curam (DCAS) |
| Client Applications	| Applications (Composite and Mobile) providing client access to the HBX | 
| DCAS	| DC Access System – an encapsulation of COTS products which handle some of the COTS components |
| Potential Partner (Tenant System(s))	| Plug and play components which can be connected to the HBX using the ACapi Models |
| ACapi	| API and Integration Layer – tie together DCAS, Potential Partners, EDI, DCAS Infrastructure, and External Infrastructure |
| Glue Database	| Glue DB – Integration Layer Authority System for Exchange Ops |
| DCAS Infrastructure	| DCAS Supporting Systems and Integration Components |
| EDI Infrastructure | Carrier Transaction Interface supporting the HBX – the Integration Layer |
| External Infrastructure |	External Systems – necessary for eligibility and other functions |
| Individual Eligibility & Plan Shopping |  |


### External Services 
| Component	| DCHBX Component | 
| --------- | --------------- |
| FDISH | Federal Web service gateway: DHS, DHHS, SSA, IRS, |
| Local Hub | DC DMV, DHS, |

