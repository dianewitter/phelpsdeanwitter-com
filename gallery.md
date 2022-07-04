---
body-class: gallery
title: Gallery
custom-css: gallery
description: Media gallery of Phelps Dean Witter.
---

{% for item in site.data.gallery %}
	{%- if item.hide -%}
	{%- continue -%}
	{%- endif -%}
<div>
{% if item.video-filename != null %}
<video controls poster="{{ 'assets/gallery/' | append: item.poster | relative_url }}">
	<source src="{{ 'assets/gallery/' | append: item.video-filename | relative_url 	}}" />
</video>
{% else %}
<img src="{{ 'assets/gallery/' | append: item.filename | relative_url }}" />
	{% endif %}
	{%- if item.caption %}
<p>{{ item.caption }}</p>
	{%- endif -%}
</div>
{% endfor %}