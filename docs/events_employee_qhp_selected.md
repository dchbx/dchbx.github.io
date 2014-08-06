---
layout: default
title: Events/Employee QHP Selected
---
## Event Name
Employee QHP Plan Selected

## Event URN
```Ruby
urn:openhbx:events:v1:employers_employees#qhp_selected
```

## Purpose
The event notifies subscribers and listeners that an employee has selected a QHP in the HBX

## Trigger
Event is published by the HBX plan shopping resource when an employee has selected a QHP in the HBX

## Message Composition

### Header
| Element | Type | Min..Max | Description |
| ------- | ---- | -------- | ----------- |
| hbx_id              | xs:string   | 1..1 | CMS-assigned Health Benefit Exchange identifier |
| submitted_timestamp | xs:dateTime | 1..1 | UTC date and time when event occurred |
| authorization       | xs:string   | 1..1 | Authentication/authorization credentials |
| message_id          | xs:string   | 0..1 | Value that uniquely identifies this message |
| originating_service | xs:anyURI   | 1..1 | The URN of service that posted event |
| correlation_id      | xs:string   | 0..1 | Attribute to associate the current message with previous or application-specific message |

### Event
| Element | Type | Min..Max | Description
| ------- | ---- | -------- | ---------- |
| event_name | EmployerEmployeeEventNameType | 1..1 | Event notification type for SHOP employee |
| qualifying_reason | xs:anyURI | 0..1 |  Reason event generated |
| employer_uri | EmployerType | 1..1 | Employer associated with the Employee
| enrollmentl_group_uri | EnrollmentGroupType  | 0..N | Employer associated with the Employee |
| body | ServiceBodyType | 0..1 | Optional - EmployerType restriction

## Request Payload
```
Request Payload (to be added)
```

## Response Payload
```
Response Payload (to be added)
```

