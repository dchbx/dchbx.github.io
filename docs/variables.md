---
layout: default
title: Variables
---

### Resource Table from Collection ###

| Resource	| Description |
| --------- | ----------- |{% for q in site.resources %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}

### Employer Requests Table from Collection ###

| Resource	| Description |
| --------- | ----------- |{% for q in site.resourcesemployerreq %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}

## Collection Variables ##
{% for q in site.resources %}
### {{ q.title }} ###
path = {{ q.path }}<br>
relative_path = {{ q.relative_path }}<br>
url = {{ q.url }}<br>
collection_name = {{ q.collection }}<br>
<p>
{% endfor %}


