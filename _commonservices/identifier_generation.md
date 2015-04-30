---
layout: default
title: "Identifiers Service"
description: "The Identifiers service exposes generation of unique identifiers."
iteratortitle: "Identifiers"
---

### Purpose
The Identifiers service generates globabally unique identifies within a specified domain.

Identifiers are in the form of an integer-based auto-incrementing sequence.

Identifiers generated for a given domain are one-use - once generated these identifiers will never again be presented to any other client.  Identifier creation is atomic - no two clients will ever receive overlapping identifiers in the same domain.

### Usage
Clients submit a request to the service with a specified domain namespace and a count specifying the number of requested identifiers to generate.

#### Inputs

| Parameter | Description |
| --------- | ----------- |
| count | The number of identifiers to generate - defaults to 1. |
| sequence_name | The domain in which the identifier exists.  Required.  Currently allowed values are: policy_id, member_id, irs_group_id, e_case_id. |
	
#### Outputs
The returned body is a payload containing the generated identifiers as a JSON array.

#### HTTP Bindings

| Parameter | Encoding |
| --------- | -------- |
| count | query string |
| sequence_name | URI |

##### HTTP Request

        GET /sequences/<sequence_name>(?count=<count>)
        GET /sequences/policy_id?count=4

##### HTTP Response

	[188855,188856,188857,188858]

#### AMQP Bindings

| Message Property | Value |
| --- | ----- |
| Exchange | Request Exchange |
| Routing Key | sequence.next |

| Parameter | Encoding |
| --------- | -------- |
| count | headers |
| sequence_name | headers |
