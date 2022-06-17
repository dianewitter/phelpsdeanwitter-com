---
body-class: performances
title: Performances
custom-css: performances
---

{% assign sorted_meta = site.data.media | sort: "year" %}
<ul>
{% for performance in sorted_meta reversed %}
<li class="
    {%- if performance.youtube-audio -%}
    mostly-audio
    {%- endif %}
    {% if performance.youtube-video -%}
    contentful-video
    {%- endif -%}
"><h2 id="{{ performance.title | slugify }}">{{ performance.title | smartify }} ({{ performance.year }})</h2>

<p class="details">
{{ performance.details }}
</p>

<div class="mostly-audio">
{%- if performance.youtube-audio -%}
{%- include youtube-embed.html youtube-id=performance.youtube-audio -%}
{%- endif -%}
</div>

{%- if performance.youtube-video -%}
<div class="contentful-video">
{%- include youtube-embed.html youtube-id=performance.youtube-video -%}
</div>
{%- endif -%}

</li>
{% endfor %}
</ul>