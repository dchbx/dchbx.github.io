---
layout: default
title: Variables
---

## Variables ##

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

### Page Title ###
{{ page.title }}

### Page URL ###
{{ page.url }}