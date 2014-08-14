---
layout: default
title: Variables
---

## Collection Variables ##
{% for q in site.resources %}
### {{ q.title }} ###
path = {{ q.path }}<br>
relative_path = {{ q.relative_path }}<br>
url = {{ q.url }}<br>
collection_name = {{ q.collection }}<br>
<p>
{% endfor %}

### Resource Table ###

| Resource	| Description |
| --------- | ----------- |{% for q in site.resources %}
| [{{ q.iteratortitle }}]({{ q.url }}) | {{ q.description }} |<br>{% endfor %}

| Resource	| Description |
| --------- | ----------- |
| [Employer](/docs/resources_employer) | Employers are groups that contain Employees and is specific to the HBX domain SHOP or Business marketplace.  Employers offer open enrollment periods for Employees to be able to select Qualifying Health Plans provided through Carriers and Brokers associated with the Employer.  The Employer Resource accounts for Resource Requests and Events associated with the Employee. | 
| [Individual](/docs/resources_individual) | An Individual represents the discrete unit of insured in the HBX.  Individuals enroll, determine eligibility, and select plans outside of the Employer/Employee relationship.  The Individual marketplace is distinct from the SHOP/Business marketplace. | 
| [Policy](/docs/resources_policy) | Policy is a grouping that binds a set of Resources together under a session or key within the HBX. |

### Site Title ###
{{ site.title }}

### Site Description ###
{{ site.description }}

### Site BaseURL ###
{{ site.baseurl }}

### Site URL ###
{{ site.url }}

### Site Pages ###
{% for p in site.pages %}
  {% if p.title %}<a {% if p.url == page.url %}class="active"{% endif %} href="{{ p.url | prepend: site.baseurl }}">{{ p.title }}</a> | {% endif %}
{% endfor %}

## Page Variables ##

### Page Title ###
{{ page.title }}

### Page URL ###
{{ page.url }}
