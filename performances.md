---
body-class: performances
title: Performances
custom-css: performances
description: Performance and recordings of Phelps Dean Witter's works.
---

<div>
<div style="background: linear-gradient(rgb(31, 36, 47), rgb(7,8,10)); border-radius: 10px; padding: 10px 0 10px 10px;">
<iframe style="margin: 0;" src="https://open.spotify.com/embed/album/7oFDfViIZ8DdtOepnxGuVA?utm_source=generator" width="100%" height="380" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
</div>
</div>

<div>
<iframe allow="autoplay *; encrypted-media *;" frameborder="0" height="450" style="width:100%;max-width:660px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.music.apple.com/us/album/phelps-dean-witter-collected-works-1980-2022/1647993744"></iframe>
</div>

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

{%- if performance.spotify-playlist -%}
<div class="contentful-video">
{{ performance.spotify-playlist }}
</div>
{%- endif -%}

{%- if performance.youtube-audio -%}
<div class="mostly-audio">
{%- include youtube-embed.html youtube-id=performance.youtube-audio -%}
</div>
{%- endif -%}

{%- if performance.youtube-video -%}
<div class="contentful-video">
{%- include youtube-embed.html youtube-id=performance.youtube-video -%}
</div>
{%- endif -%}

</li>
{% endfor %}
</ul>