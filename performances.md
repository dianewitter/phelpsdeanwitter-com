---
body-class: performances
title: Performances
custom-css: performances
---

{% assign sorted_meta = site.data.media | sort: "year" %}
<ul>
{% for performance in sorted_meta reversed %}
<li><h2 id="{{ performance.title | slugify }}">{{ performance.title | smartify }} ({{ performance.year }})</h2>

{{ performance.details }}

{%- if performance.youtube-video[0] -%}
	{%- for video in performance.youtube-video -%}
{%- include youtube-embed.html youtube-id=video -%}
	{%- endfor -%}
{%- else -%}
{%- include youtube-embed.html youtube-id=performance.youtube-video -%}
{%- endif -%}

</li>
{% endfor %}
</ul>