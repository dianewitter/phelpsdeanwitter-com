---
body-class: works
title: Works
---

{%- for ensemble in site.data.works %}
## {{ ensemble.type }}
    {%- if ensemble.subtypes != null -%}
        {%- for subtype in ensemble.subtypes %}
### {{ subtype.type }}
            {%- include works-list.html works=subtype.works -%}
        {%- endfor -%}
    {%- else -%}
        {%- include works-list.html works=ensemble.works -%}
    {%- endif -%}
{%- endfor -%}