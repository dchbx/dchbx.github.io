---
layout: default
title: Services/Transform
---

# Transform

## Purpose
The Transform service performs two major tasks – transformation and validation.  The service is used to transform client request payloads and validate the result.  Clients may also elect to use the service to validate without transforming.

The Integration Layer of the OpenHBX operations using CV XML.  The Transform service is provided to allows OpenHBX clients a common mechanism to transform their XML into CV and out of CV or into or out of formats of their choice.

Clients are free to use this service whether or not they require follow up requests to the Integration Layer for other Common Services or for Resource Operations and Events.

## Usage
The Transform service design allows clients to submit a payload and a URI reference to a transform  (XSLT).  The service will access the supplied transform, apply it to the payload, and return the transformed The Integration Layer wishes to operate strictly in CV XML.  However, clients may use this service prior to calling other Common Services to obtain CV representations of their data

### Inputs

| Input	 | Description |
| ------ | ----------- |
| Payload	| Payload supplied by the client request to be transformed and/or validated. |
| XSLT URI / Location Reference	| Reference to the XSLT style sheet service will use to transform the payload. |
| Reply | Information	Reply information. |
	
### Outputs

### WSDL

#### Request

	Request Payload

#### Response

	Response Payload
