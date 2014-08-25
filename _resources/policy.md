---
layout: default
title: "Policy Resource"
description: "Policy is a grouping that binds a set of Resources together under a session or key within the HBX. It represents a Person or Member covered under a Qualifying Health Plan with a start date and a stop date, in other words, for a specific period of time."
iteratortitle: "Policy"
---

Policy is a grouping that binds a set of Resources together under a session or key within the HBX. It represents a Person or Member covered under a Qualifying Health Plan with a start date and a stop date, in other words, for a specific period of time.

### Policy Requests and Events

#### Policy Requests
This table enumerates the Policy Resource Requests:

| Request	 | Description / Provides |
| --------- | ----------- |{% for q in site.resourcespolicyreq %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}
| create	| Creates or registers an Individual.  | 
| update	| Updates an Individual.  | 
| delete	| Deletes an Individual.  |

#### Policy Events

This table enumerates the Policy Resource Events:

| Event	| Description /Trigger Mechanism |
| --------------------  | ----------- |
| created	 | Individual registers or is added to the HBX. |
| updated	| Individual updates information to the HBX. |
| deleted	| Individual is deleted from the HBX. |