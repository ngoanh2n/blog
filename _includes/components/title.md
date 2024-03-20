<!-- LOCATION -->
<!-- _includes/components/ -->

<!-- INCLUDE -->
<!-- components/title.md -->

<!-- VARIABLES -->
<!-- level:  {VALUE} | Example: ### -->
<!-- value:  {VALUE} | Example: Appium -->
<!-- anchor: {VALUE} | Example: my-anchor -->


<!-- READ VARIABLES -->
{% assign level  = include.level %}
{% assign value  = include.value %}
{% assign anchor = include.anchor %}


<!-- MAIN CONTENT -->

<!-- PASSED LEVEL,  -->
{% if level != nil %}

<!-- -- PASSED ANCHOR -->
{% if anchor != nil %}
{{ level }} {{ value }} {#{{ anchor }}}

<!-- -- NOT PASSED ANCHOR -->
{% else %}
{{ level }} {{ value }}
{% endif %}

<!-- -- LEVEL="#" OR LEVEL="##" -->
{% if level == "#" or level == "##" %}
<hr>{: .head-hr }
{% endif %}

<!-- NOT PASSED LEVEL,  -->
{% else %}
<h1>{{ value }}</h1>
<hr>{: .head-hr }
{% endif %}
