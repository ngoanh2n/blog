<!-- _includes/docs/env/chocolatey/ -->

<!-- USE CASE -->
<!-- 1. include docs/env/chocolatey/title.md -->
<!-- 2. include docs/env/chocolatey/title.md heading="###" -->

{% assign stm = "Chocolatey" %}
{% assign heading = include.heading %}

{% if heading %}
{{heading}} {{stm}}
{% else %}
<h1>{{stm}}</h1>
{% endif %}
<hr>{: .head-hr }
