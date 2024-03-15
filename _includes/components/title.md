<!-- LOCATION -->
<!-- _includes/components/ -->

<!-- INCLUDE -->
<!-- components/title.md -->

<!-- VARIABLES -->
<!-- heading:   {HEADING} | Example: ### -->
<!-- value:     {VALUE} | Example: Appium -->


<!-- READ VARIABLES -->
{% assign heading = include.heading %}
{% assign value = include.value %}


<!-- MAIN CONTENT -->

{% if heading %}
{{ heading }} {{ value }}
{% else %}
<h1>{{ value }}</h1>
{% endif %}

{% if heading == "#" or heading == "##" %}
<hr>{: .head-hr }
{% endif %}