---
layout: default
title: "Employer Request by Identifiers"
description: "Retrieve Employer Details by Specified Identifiers"
iteratortitle: "By Identifiers"
---
## Request Name
SHOP Employer Request by Identifiers

## Purpose
Provide request methods to retrieve SHOP employer information from the HBX.

## Request URN
```
	urn:openhbx:requests:v1:employers/<primary_key>, or
	urn:openhbx:requests:v1:employers?hbx_id=<hbx_id>, or
	urn:openhbx:requests:v1:employers?fein=<fein_id>
```

## Message Composition

### Header (*ServiceHeaderType*)
Header elements are common to requests and responses

| Element | Type | Min..Max | Description |
| ------- | ---- | -------- | ----------- |
| hbx_id              | xs:string   | 1..1 | CMS-assigned Health Benefit Exchange identifier |
| submitted_timestamp | xs:dateTime | 1..1 | UTC date and time when event occurred |
| status              | ServiceStatusType | 1..1 | Service call return status |
| authorization       | xs:string   | 1..1 | Authentication/authorization credentials |
| message_id          | xs:string   | 0..1 | Value that uniquely identifies this message |
| originating_service | xs:anyURI   | 1..1 | The URN of service that posted event |
| reply_to            | xs:anyURI   | 0..1 | Designated the consumer service urn endpoint where to transmit response |
| correlation_id      | xs:string   | 0..1 | Attribute to associate the current message with previous message ID or application-specific message |

### Request (*EmployerRequestType*)
| Element | Type | Min..Max | Description
| ------- | ---- | -------- | ---------- |
| request_name | EmployerRequestNameType | 1..1 | Request type for SHOP employer |
| parameters   | xs:anyURI | 0..1 |  Request parameters |
| metadata     | ServiceMetadataType | 0..1 | Metadata associated with the request
| body         | ServiceBodyType | 0..1 | Optional - EmployerType restriction

### Response (*EmployerResponseType*)
| Element | Type | Min..Max | Description
| ------- | ---- | -------- | ---------- |
| metadata     | ServiceMetadataType | 0..1 | Metadata associated with the response
| body         | ServiceBodyType | 0..1 | Optional - EmployerType restriction


## Request
```
By Primary Key:

	urn:openhbx:requests:v1:employers/<primary_key>

By HBX ID:

	urn:openhbx:requests:v1:employers?hbx_id=123456

By FEIN:

	urn:openhbx:requests:v1:employers?fein=123456789
```

## Response Payload
```
<?xml version="1.0"?>
<n1:employers xsi:schemaLocation="http://openhbx.org/api/terms/1.0 employer.xsd" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:n1="http://openhbx.org/api/terms/1.0">
  <n1:employer>
    <n1:name>Employer XYZ, LLP</n1:name>
    <n1:fein>123456789</n1:fein>
    <n1:hbx_uri>http://<hostname>:<port>/employers/53d263eaeb899a9d4102a2d9</n1:hbx_uri>
    <n1:hbx_id>123456</n1:hbx_id>
    <n1:sic_code/>
    <n1:fte_count>8</n1:fte_count>
    <n1:pte_count>0</n1:pte_count>
    <n1:open_enrollment_start>2013-12-18</n1:open_enrollment_start>
    <n1:open_enrollment_end>2013-12-23</n1:open_enrollment_end>
    <n1:plan_year_start>2014-01-01</n1:plan_year_start>
  </n1:employer>
</n1:employers>
```

