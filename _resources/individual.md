---
layout: default
title: "Individual (Person) Resource"
description: "An Individual represents the discrete unit of insured in the HBX.  Individuals enroll, determine eligibility, and select plans outside of the Employer/Employee relationship.  The Individual marketplace is distinct from the SHOP/Business marketplace."
iteratortitle: "Individual (Person)"
---

The Individual (Person) is the unit of insured in the HBX.

### Individual Requests and Events

#### Individual Requests
This table enumerates the Individual Resource Requests:

| Request	 | Description / Provides |
| --------- | ----------- |{% for q in site.resourcesindividualreq %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}
| create	| Creates or registers an Individual.  | 
| update	| Updates an Individual.  | 
| delete	| Deletes an Individual.  |

#### Individual Events

This table enumerates the Individual Resource Events:

| Event	| Description /Trigger Mechanism |
| --------------------  | ----------- |
| created	 | Individual registers or is added to the HBX. |
| updated	| Individual updates information to the HBX. |
| deleted	| Individual is deleted from the HBX. |