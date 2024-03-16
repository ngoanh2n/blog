<!-- LOCATION -->
<!-- _includes/components/ -->

<!-- INCLUDE -->
<!-- components/title.md -->

<!-- VARIABLES -->
<!-- heading:   {HEADING} | Example: ### -->
<!-- value:     {VALUE} | Example: Appium -->
<!-- anchor:    {VALUE} | Example: my-anchor -->


<!-- READ VARIABLES -->
{% assign heading = include.heading %}
{% assign value   = include.value %}
{% assign anchor  = include.anchor %}


<!-- MAIN CONTENT -->

{% if anchor == nil %}
{{ heading }} {{ value }}
{% else %}
{{ heading }} {{ value }} {#{{ anchor }}}
{% endif %}

{% if heading == "#" or heading == "##" %}
<hr>{: .head-hr }
{% endif %}
