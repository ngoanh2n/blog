<!-- _includes/docs/env/java/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/java/title.md -->
<!-- 2. include docs/env/java/title.md heading="###" -->

{% assign stm = "Java" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
