---
body-class: works
title: Works
custom-css: works
description: Complete list of works composed by Phelps Dean Witter.
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