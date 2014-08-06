---
layout: default
title: Events/Employee QHP Selected
---
## Event Name
employee_qhp_plan_selected

## Event URN
urn:openhbx:events:v1:employers_employees#qhp_selected

## Purpose
The event notifies subscribers and listeners that an employee has selected a QHP in the HBX

## Trigger
Event is published by the HBX plan shopping resource when an employee has selected a QHP in the HBX

## Message Composition

### Header
| Element | Type | Min..Max | Description |
| ------- | ---- | -------- | ----------- |
| hbx_id              | xs:string | 1..1 | CMS-assigned Health Benefit Exchange identifier
| submitted_timestamp | xs:dateTime | 1..1 | UTC date and time when event occured
| authorization       |  | 1..1 | Authentication/authorization credentials
| message_id          | xs:string | 0..1 | Value that uniquely identifies this message
| originating_service |  | 1..1 | The URN of service that posted event
| correlation_id      | xs:string | 0..1 | Attribute to associate the current message with previous or application-specific message


### Event
| Element | Type | Min..Max | Description
| ------- | ---- | -------- | ---------- |
| event_name        | EmployerEventNameType | 1..1 | 
| employer_uri      | xs:anyURI | 1..1 |
| body | EmployerType | 0..1 | Optional 


## Request Elements
The event request must contain at least the following request elements:

| Request Element	| Description |
| ----------------- | ----------- |
| employer_id	| Employer id associated with the employee who selected the QHP. |
| employer_uri	| The URI to access the specific employer associated with this employee QHP selection. |
| employee_id	| Employee id associated with the employee who selected the QHP. |
| employee_uri	| The URI to access the employee who selected the QHP. |
| plan_id	| The QHP plan id of the plan the employee selected. |
| plan_uri	| The URI to access the specific QHP selected. |

## Transport Elements

| Protocol	 | Elements as |
| ---------- | ----------- |
| HTTP	     | GET Parameters, POST Parameters | 
| JMS	     | Message Properties | 
| AMQP	     | Message Headers | 

## Request Payload

    Request Payload

## Response Payload
	
	Response Payload

