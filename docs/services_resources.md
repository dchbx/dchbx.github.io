---
layout: default
title: Service Resources
---

The ACApi exposes the following HBX Service Resources.  Each Resource has an associated set of Requests and Events.  Requests are functions or operations that can be called to perform actions on the Resource or to retrieve information about the Resource.  Events are notifications triggered by specific occurrences in the HBX.

Each specific Resource page describes Requests, Events, the basics of crafting a request, and expected response objects.  Resource pages will become accessible as they are defined and made available in the ACApi.

| Resource	| Description |
| --------- | ----------- |{% for q in site.resources %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}
