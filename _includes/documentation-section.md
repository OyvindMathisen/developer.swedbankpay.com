{%- capture sections -%}
    checkout-v2,
    checkout-v3/enterprise,
    checkout-v3/starter,
    checkout-v3/business,
    checkout-v3/payments-only,
    payment-menu,
    gift-cards,
    card,
    invoice,
    mobile-pay,
    swish,
    trustly,
    vipps
{%- endcapture -%}
{%- assign sections = sections | strip_newlines | strip | split: "," -%}
{%- for s in sections -%}
    {%- assign section = s | strip_newlines | strip -%}
    {%- assign path_section = section | prepend: "/" | append: "/" -%}
    {%- if page.dir contains path_section -%}
        {%- assign documentation_section = section -%}
        {%- break -%}
    {%- endif -%}
{%- endfor -%}
{%- if documentation_section == undefined or documentation_section == nil or documentation_section == empty -%}
    {{- include.fallback -}}
{%- else -%}
    {{- documentation_section -}}
{%- endif -%}
