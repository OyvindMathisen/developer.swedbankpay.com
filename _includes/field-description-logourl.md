{%- capture documentation_section -%}{%- include documentation-section.md -%}{%- endcapture -%}
{%- capture logo_description -%}
    {%- if documentation_section == "payment-menu" or documentation_section contains "checkout" -%}
    With permission and activation on your contract, sending in a `logoUrl` will
    replace the Swedbank Pay logo with the logo sent in. If you do not send in a
    `logoUrl`, then no logo and no text is shown. Without permission or activation
    on your contract, sending in a `logoUrl` has no effect. Read more about this in
    [Custom Logo](/{{ documentation_section }}/features/optional/custom-logo).
    {%- else -%}
    The URL that will be used for showing the customer logo. Must be a picture
    with maximum 50px height and 400px width. Requires HTTPS.
     {%- endif -%}
{%- endcapture -%}
{{- logo_description | strip_newlines -}}
{%- comment -%}
The dashes in the Liquid code tags remove output space. More on that here:

<https://shopify.github.io/liquid/basics/whitespace/>

It's essential to have control over newlines in this file. If unintentional
newlines sneak into what's rendered by this include, it will break all tables
it is included in, so please beware.
{%- endcomment -%}
