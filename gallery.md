---
body-class: gallery
title: Gallery
custom-css: gallery
---

{% for item in site.data.gallery %}
	{%- if item.hide -%}
	{%- continue -%}
	{%- endif -%}
### {{ item.index }}
	{% if item.video-filename != null %}
<p>
<video controls>
	<source src="{{ 'assets/gallery/originals/' | append: item.video-filename | relative_url }}" />
</video>
</p>
	{% else %}
<img src="{{ 'assets/gallery/originals/' | append: item.filename | relative_url }}" />
	{% endif %}
{% endfor %}