---
layout: default
title: Variables
---

## Site Variables ##

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

## Collection Variables ##
{% for q in site.resources %}
  {% if q.title %}<a {% if q.url == page.url %}class="active"{% endif %} href="{{ q.url | prepend: site.baseurl }}">{{ q.title }}</a> |<br> {% endif %}
{% endfor %}