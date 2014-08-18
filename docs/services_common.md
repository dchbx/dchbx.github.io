---
layout: default
title: Common Services
---

The ACApi exposes several Common Services to handle HBX business processing.

### Services

| Service	| Description |
| --------- | ----------- || Request	 | Description / Provides |
| --------- | ----------- |{% for q in site.commonservices %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}
| Authentication & Authorization | Authentication and Authorization functions |
| Directory	| Directory for Service discovery functions |
| Document Management	| Document Management functions |
| GIS	| MAR and Location-related functions |
| Transform	| XML transformation and validation functions |
| Logging & Error	| Logging & Error functions |
| SMS	| SMS / Text functions |
| SMTP	| Email functions |

### Consumers / Users

Internal Systems
- Exchange Ops Database

External Systems
- EDI

