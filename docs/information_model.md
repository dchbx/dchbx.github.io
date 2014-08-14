---
layout: default
title: Information Model
---

The Information Model is a representation of HBX data resources and associations.

The Resources provide a logical grouping of the data types.  It is organized by logical HBX Resources.  The model illustrates the concepts and relationships for the data objects – the Resources – in the domain.

**DCHBX Information Model**
![ACApi Information Model](/assets/acapi_information_model.png)

| Resource	| Description |
| --------- | ----------- |{% for q in site.resources %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}