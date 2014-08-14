---
layout: default
title: Information Model
---

The Information Model is a representation of HBX data resources and associations.

The Resources provide a logical grouping of the data types.  It is organized by logical HBX Resources.  The model illustrates the concepts and relationships for the data objects – the Resources – in the domain.

![ACApi Information Model](/assets/acapi_information_model.png)
**DCHBX Information Model**

| Resource	| Description |
| --------- | ----------- |
{% for rsrc in site.resources %}| [{{ rsrc.title }}]({{ rsrc.url }}) | {{ rsrc.description }} | <br>{% endfor %}