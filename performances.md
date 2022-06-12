---
body-class: performances
title: Performances
---

{% assign sorted_meta = site.data.media | sort: "year" %}
<ul>
{% for performance in sorted_meta reversed %}
<li><h2>{{ performance.title | smartify }} ({{ performance.year }})</h2>
	{{ performance.details }}
</li>
{% endfor %}
</ul>