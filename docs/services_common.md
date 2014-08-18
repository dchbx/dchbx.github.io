---
layout: default
title: Common Services
---

The ACApi exposes several Common Services to handle HBX business processing.

### Services

| Service	| Description |
| --------- | ----------- |{% for q in site.commonservices %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}
| Authentication & Authorization | Authentication and Authorization functions |
| Directory	| Directory for Service discovery functions |
| Document Management	| Document Management functions |
| GIS	| MAR and Location-related functions |
| Logging & Error	| Logging & Error functions |
| SMS	| SMS / Text functions |
| SMTP	| Email functions |
