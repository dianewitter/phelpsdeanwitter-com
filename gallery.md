---
body-class: gallery
title: Gallery
custom-css: gallery
---

{% for item in site.data.gallery %}
	{% if item.video-filename != null %}
<video src="{{ 'assets/gallery/originals/' | append: item.video-filename | relative_url }}" />
	{% else %}
<img src="{{ 'assets/gallery/originals/' | append: item.filename | relative_url }}" />
	{% endif %}
{% endfor %}